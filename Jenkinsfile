pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                sh 'docker build -t app .'
            }
        }
        stage('test'){
            steps{
                echo 'test'
                sh 'docker run --rm --name app -id -p 80:80 app'
                sh '/bin/nc -vz localhost 22'
                sh '/bin/nc -vz localhost 80' 
            }
            post{
                always{
                    sh 'docker container stop app'
                }
            }
        }

        stage('Push Registry'){
            steps{
                withCredentials([usernamePassword(credentialsId: '900eb646-503e-4190-9bff-8537ec3a7296', passwordVariable: 'password', usernameVariable: 'user')]) {
                echo 'PASSWORD: $password'
                echo 'USER: $user'
                sh 'docker tag app jmonterh/app:stable'
                sh 'docker push jmonterh/app:stable'
                }
            }
        }
    }
}