pipeline {
    agent any

    stages {
        
        
        stage('Sonarqube') {
            environment {
                scannerHome = tool 'SonarQubeScanner'
            }    
            steps {
                withSonarQubeEnv('sonarqube') {
                sh "${scannerHome}/bin/sonar-scanner"
            }
            timeout(time: 10, unit: 'MINUTES') {
                waitForQualityGate abortPipeline: true
                }
            }
        }
            
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
