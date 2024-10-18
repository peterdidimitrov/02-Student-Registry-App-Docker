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
    }
}