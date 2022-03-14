pipeline {
    agent any

    stages {
        
        
        stage('Sonarqube') {
            environment {
                scannerHome = tool 'sonarqube'
            }    
            steps {
                withSonarQubeEnv('sonarqube') {
                sh "${tool("Sonarqube")}/bin/sonar-scanner \
        		-Dsonar.projectKey=task2-jenkins \
			-Dsonar.sources=. \
			-Dsonar.host.url=http://localhost:9000 \
			-Dsonar.login=b0bbd80137fc651627dddf50cbb3b5dc68360393"
			}
            timeout(time: 10, unit: 'MINUTES') {
                waitForQualityGate abortPipeline: true
                }
            }
        }
            
    }
}
