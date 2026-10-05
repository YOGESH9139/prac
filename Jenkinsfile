pipeline{
    agent any
    stages {
        stage ('Checkout') {
            steps {
                echo 'Checking registration page...'
                checkout scm
            }
        }
        stage ('Build') {
            steps {
                echo 'Building registration page...'
                bat '''
                    if not exists index.html exit /b 1
                    if not exists style.css exit /b 1
                    if not exists script.js exit /b 1
                '''
                echo 'All build files exist.'
            }
        }
        stage ('Test') {
            steps {
                echo 'Testing'
            }
        }
        stage ('Complete') {
            steps {
                echo 'Donee'
            }
        }
    }
}