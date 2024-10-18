pipeline {
    agent any
    stages {
        stage('NPM Install') {
            steps {
            bat 'npm install'
            }
        }
        stage('Parallel Execution') {
            parallel {
                stage('Run npm audit tests') {
                    steps {
                        bat 'npm audit'
                    }
                }   
                stage('Execute Tests') {
                    steps {
                        bat 'npm test'
                    }
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
            bat 'Deploy to Staging'
            }
        }
        stage('Approve for Production Deployment') {
            steps {
                input message 'Approve deployment to Production?', ok: 'Deploy to Production'
            }
        }
        stage('Deploy to Production') {
            steps {
            bat 'Deploy to Production'
            }
        }
    }
}