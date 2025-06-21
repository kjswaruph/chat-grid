pipeline {
    agent any

    tools {
        maven 'Maven3'  // Use the name you configured in Global Tool Configuration
    }

    stages {
        stage('Build Backend') {
            steps {
                dir('backend') {
                    bat 'mvn clean package -DskipTests'
                }
            }
        }

        stage('Install Frontend Dependencies') {
            steps {
                dir('frontend') {
                    bat 'npm install' // or yarn install if applicable
                }
            }
        }

        stage('Run SonarQube Analysis') {
            steps {
                withSonarQubeEnv('MySonarQube') {
                    bat 'sonar-scanner'
                }
            }
        }
    }
}
