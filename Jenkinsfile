pipeline {
    agent any

    tools {
        jdk 'nish_jdk'
    }

    environment {
        SCANNER_HOME = tool 'SonarScanner'
    }

    stages {

        stage('Check Files') {
            steps {
                bat 'dir'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                bat """
                %SCANNER_HOME%\\bin\\sonar-scanner.bat ^
                -Dsonar.projectKey=tic-tac-toe ^
                -Dsonar.sources=. ^
                -Dsonar.host.url=http://localhost:9000 ^
                -Dsonar.token=YOUR_TOKEN
                """
            }
        }

        stage('Success') {
            steps {
                echo 'Frontend Project + SonarQube Analysis Successful'
            }
        }
    }
}