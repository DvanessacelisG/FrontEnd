pipeline {
    agent any
    stages {         
        stage ('Clone & Clean') {
              steps{
                    sh "git clone https://github.com/DvanessacelisG/FrontEnd.git"
                    sh "rm -rf movieanalyst-website"
              }
        }
        
        stage ('Build') {
              steps{
                    sh "zip -r movieanalyst-website.zip /var/lib/jenkins/workspace/Front"
                  
              }
        }
        
    }
}
