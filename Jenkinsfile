pipeline {
    agent any
    stages {         
        stage ('Clone & Clean') {
              steps{
                     sh "rm -rf FrontEnd"        
              }
        }
        stage ('Build') {
              steps{
                  dir('/var/lib/jenkins/workspace/'){
                   // sh "zip -r movieanalyst-website.zip movieanalyst-website"
                  sh "tar -zcvf movieanalyst-website.tar.gz FrontE_master"
                  }
              }
        }
          stage ('FrontA') {
              steps{
                  dir('/var/lib/jenkins/workspace/'){
            sshPublisher(publishers: [sshPublisherDesc(configName: 'ubuntu@12.0.1.27', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'tar zxvf movieanalyst-website.tar.gz', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'movieanalyst-website.tar.gz')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])}}          }
        stage('FrontB'){
            steps{
                dir('/var/lib/jenkins/workspace/'){
            sshPublisher(publishers: [sshPublisherDesc(configName: 'ubuntu@12.0.1.27', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'tar zxvf movieanalyst-website.tar.gz', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'movieanalyst-website.tar.gz')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])                }
            }
        }
    }
}
