pipeline {
    agent any
    tools {
        nodejs 'Nodejs'
    }
    stages {
        stage('Clonar repositorio') {
            steps {
                git(
                    url: "https://github.com/AnderMichael/Calculator_Sum.git",
                    branch: "main",
                    changelog: true,
                    poll: true
                )
            }
        }
        stage('Instalar Jenkins'){
            steps{
                sh 'npm install'
            }
        }
        stage('Unit Tests') { 
            steps {
                echo 'Testing 1...'
                sh 'npm run test' 
            }
        }
        stage('Integration Tests'){
            steps{
                echo 'Testing 2...'
                sh 'npm run e2e'
            }
        }
    }
}