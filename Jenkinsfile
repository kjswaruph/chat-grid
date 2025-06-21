pipeline {
    agent any

    environment {
        SONAR_SCANNER_HOME = tool 'SonarScanner'
    }


     stages {
        stage('Build Backend') {
            steps {
                dir('backend') {
                    bat 'docker build -t my-backend .'
                }
            }
        }

         
        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('MySonarQube') {
                    bat "${SONAR_SCANNER_HOME}/bin/sonar-scanner"
                }
            }
        }
    }
}
