pipeline {
    agent any
    
stages {
        
	stage('build') {
            steps {
                bat 'mvn clean install'
            }
               }
         stage('Code review') {
            steps {
               def scannerHome = tool 'SonarScanner';
               sh "${scannerHome}/bin/sonar-scanner"
            }

        }
    }
}
