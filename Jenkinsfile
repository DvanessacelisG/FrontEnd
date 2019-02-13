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
                  sh "tar -zcvf movieanalyst-website.tar.gz test000_master"
                  }
              }
        }
          stage ('FrontA') {
              steps{
                  dir('/var/lib/jenkins/workspace/'){
                sshPublisher(publishers: [sshPublisherDesc(configName: 'ubuntu@12.0.1.27', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'movieanalyst-website.tar.gz', useAgentForwarding: true)], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])                  }     
              } 
          }
        stage('FrontB'){
            steps{
                dir('/var/lib/jenkins/workspace/'){
                sshPublisher(publishers: [sshPublisherDesc(configName: 'ubuntu@12.0.2.189', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'movieanalyst-website.tar.gz', useAgentForwarding: true)], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])             }
        }
        }
    }
}
