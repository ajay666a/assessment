pipeline {
    agent any
    stages {
        stage('Example Deploy') {
            when {
                branch 'test'
            }
            steps {
                echo 'Deploying into main branch'
            }
        }
    }
}
