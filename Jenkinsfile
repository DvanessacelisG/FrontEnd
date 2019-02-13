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
                    sh "zip -r movieanalyst-website.zip /var/lib/jenkins/workspace/"
                  
              }
        }
          stage ('ssh') {
              steps{
                    sh "scp -i /home/ubuntu/AWS/VanessaCelis.pem /var/lib/jenkins/workspace/test1_master/movieanalyst-website.zip ubuntu@12.0.1.27:/home/ubuntu"
                  
              }
        }      
        
        
    }
}
