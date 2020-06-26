pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                bat 'mvn clean install'
            }
            stage('Code review') {
            steps {
               def scannerHome = tool 'SonarScanner';
    withSonarQubeEnv('My SonarQube Server') { // If you have configured more than one global server connection, you can specify its name
      sh "${scannerHome}/bin/sonar-scanner"
            }
        }
    }
}
