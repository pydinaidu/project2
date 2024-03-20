pipeline{
  agent any
  stages{
    stage("Git Checkout"){
      steps{
            git credentialsId: 'github', url: 'https://github.com/pydinaidu/project2.git'
           }
          }
     stage("Maven Build"){
       steps{
            sh "mvn clean package"
           // sh "mv target/*.war target/project2.war"
             }
            }
     stage("deploy-dev"){
       steps{
          sshagent(['tomcat-deploy']) {
          sh """
          scp -o StrictHostKeyChecking=no target/project2.war  
          ubuntu@170.20.3.29:/opt/tomcat/webapps/
          ssh ubuntu@170.20.3.29 /opt/tomcat/bin/shutdown.sh
          ssh ubuntu@170.20.3.29 /opt/tomcat/bin/startup.sh
           """
            }
          }
        }
      }
    }