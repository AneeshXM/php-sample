pipeline {
    agent any

    stages {
        stage('Deploy PHP Webapplication') {
            steps {
                sshPublisher(publishers: [sshPublisherDesc(configName: 'apache', transfers: [sshTransfer(
                    cleanRemote: false, 
                    excludes: '', 
                    execCommand: 'sudo systemctl restart apache2', // Restart Apache after deployment
                    execTimeout: 120000, 
                    flatten: false, 
                    makeEmptyDirs: false, 
                    noDefaultExcludes: false, 
                    patternSeparator: '[, ]+', 
                    remoteDirectory: '/var/www/html/', 
                    remoteDirectorySDF: false, 
                    removePrefix: '', 
                    sourceFiles: '**/*.*'
                )], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
    }
}

