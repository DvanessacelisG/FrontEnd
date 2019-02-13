pipeline {
    agent any
    stages {         
        stage ('Clone & Clean') {
              steps{
                    sh "rm -rf movieanalyst-website"
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
                    sh "scp -i /home/ubuntu/AWS/VanessaCelis.pem /var/lib/jenkins/workspace/movieanalyst-website.zip ubuntu@12.0.1.27:/home/ubuntu"
                  
              }
        }      
        
        
    }
}
