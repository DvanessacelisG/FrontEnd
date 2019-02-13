pipeline {
    agent any
    stages {         
        stage ('Clone & Clean') {
              steps{
                     sh "rm -rf FrontEnd"
                    sh "git clone https://github.com/DvanessacelisG/FrontEnd.git" 
                   
              }
        }
        stage ('Build') {
              steps{
                    sh "zip -r movieanalyst-website.zip /var/lib/jenkins/workspace/"
                  
              }
        }
          stage ('ssh') {
              steps{
                    sh "scp -i /home/ubuntu/AWS/VanessaCelis.pem -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/test000_master/movieanalyst-website.zip ubuntu@12.0.1.27:/home/ubuntu"
                    sh "unzip movieanalyst-website..zip -d movieanalyst-website." 
              }
        }      
        
        
    }
}
