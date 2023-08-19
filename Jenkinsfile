pipeline {
    agent any
    stages {
        stage('Build') {
            when {
                beforeAgent true
                branch "feature1"
            }
            steps {
                echo "Hello"                
        }          
    }
}}
