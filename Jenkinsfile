pipeline {
    agent any
    stages {
        stage('Example Deploy') {
            when {
                branch 'prod'
            }
            steps {
                echo 'Deploying into main branch'
            }
        }
    }
}



