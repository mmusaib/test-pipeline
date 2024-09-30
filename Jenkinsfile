pipeline{
    agent any
    stages{
        stage('Production'){
            when{
                branch 'main'
            }
            steps{
                sshPublisher(publishers: [sshPublisherDesc(configName: 'iceboxEbay', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/var/www/html', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '**/*.*')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
        stage('Development/Staging'){
            when{
                branch 'staging'
            }
            steps{
                sshPublisher(publishers: [sshPublisherDesc(configName: 'iceboxEbay', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/var/www/html/staging', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '**/*.*')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
    }
}