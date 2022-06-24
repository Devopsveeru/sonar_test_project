pipeline{
  agent any
  stages{
     stage("Maven Build"){
       steps{
            sh "mvn clean package"
        }
     }
     stage('sonar_test') {
       steps{
           withSonarQubeEnv('sonar_test') { // If you have configured more than one global server connection, you can specify its name
           sh "${sonar_test}/home/ec2-user/sonar-runner-2.4 sonar:sonar"
           }    
        }
     }
    } 
}            
