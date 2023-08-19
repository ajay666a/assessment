pipeline {
    agent any
    stages {
        stage('Build') {
            when {
                branch 'dev'
            }
            steps {
                s3Upload consoleLogLevel: 'INFO', dontSetBuildResultOnFailure: false, dontWaitForConcurrentBuildCompletion: false, entries: [[bucket: 'apache-files', excludedFile: '', flatten: false, gzipFiles: false, keepForever: false, managedArtifacts: false, noUploadOnFailure: true, selectedRegion: 'ap-south-1', showDirectlyInBrowser: false, sourceFile: 'index.html', storageClass: 'STANDARD', uploadFromSlave: false, useServerSideEncryption: false]], pluginFailureResultConstraint: 'FAILURE', profileName: 'awscredentials', userMetadata: []
            }
        }
        stage('SSH transfer') {
            when {
                branch 'dev'
            }
            steps {
                sshPublisher(
                    continueOnError: false, failOnError: true,
                    publishers: [
                        sshPublisherDesc(
                            configName: "Apache",
                            verbose: true,
                            transfers: [
                                sshTransfer(
                                    sourceFiles: "index.html",
                                    remoteDirectory: "/var/www/html",
                                    )
                                ])])
            }
        }
          
    }
}
