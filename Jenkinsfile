pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                sh 'docker build -t app'
            }
        }
        stage('test'){
            steps{
                echo 'test'
            }
        }

        stage('deploy'){
            steps{
                echo 'deploy'
            }
        }
    }
}