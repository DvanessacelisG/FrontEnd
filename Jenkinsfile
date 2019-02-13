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
                    sh "cd .."
                    sh "zip -r movieanalyst-website.zip movieanalyst-website"
                  
              }
        }
          stage ('FrontA') {
              steps{
              sshPublisher(publishers: [sshPublisherDesc(configName: 'ubuntu@12.0.1.27', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'echo "FrontA"', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'movieanalyst-website.zip', useAgentForwarding: true)], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])            
                   }
        }      
        
        stage('FrontB'){
            steps{
               sshPublisher(publishers: [sshPublisherDesc(configName: 'ubuntu@12.0.2.189', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'echo "FrontB"', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'movieanalyst-website.zip', useAgentForwarding: true)], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
             }
        }
    }
}
