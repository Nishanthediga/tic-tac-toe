pipeline {
    agent any

    stages {

        stage('Check Files') {
            steps {
                bat 'dir'
            }
        }

        stage('Success') {
            steps {
                echo 'Frontend Project Build Successful'
            }
        }
    }
} 