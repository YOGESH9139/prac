pipeline {
    agent any
    stages {
        stage ('Checkout') {
            steps {
                echo 'Checking out sourc code...'
                checkout scm
            }
        }
        stage ('Build') {
            steps {
                echo 'Building user registration application...'
                bat '''
                    if not exists index.html exit /b 1
                    if not exists style.css exit /b 1
                    if not exists script.js exit /b 1
                '''
                echo 'All required files are present.'
            }
        }
        stage ('Test') {
            steps {
                echo 'Running basic application validation...'
                bat '''
                    findstr /C:"<form" index.html >nul
                    if errorlevel 1 exit /b 1
                '''
                echo 'Basic validation passed.'
            }
        }
        stage ('Complete')
    }
}