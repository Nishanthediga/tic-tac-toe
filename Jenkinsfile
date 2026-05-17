pipeline {
    agent any

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
                -Dsonar.token=squ_9202e0499cad49b9979cfe47ca459030d703970b
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