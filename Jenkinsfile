pipeline {
    agent any
    stages {
        stage('Build') {
            when {
                git branch: 'main'
            }
            steps {
                echo "Hello"                
        }          
    }
}}
