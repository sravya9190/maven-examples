node {
   
   stage('Code Checkout') { // for display purposes
   git credentialsId: '15f9d41b-09f9-49bf-83e7-e156a079e1f1', url: 'https://github.com/sravya9190/maven-examples.git'
   }
   stage('Build') {
    withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
     sh 'mvn clean compile'
     } 
   }
   stage('UnitTest run') {
    withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
     sh 'mvn test'
     }   
   }
   stage('Code Quality') {
     withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
     sh 'mvn sonar:sonar \
        -Dsonar.projectKey=new-org \
  -Dsonar.organization=new-org \
  -Dsonar.host.url=https://sonarcloud.io \
  -Dsonar.login=972d86d7fb9a7ebe0422e5168259d71edbbf4558 


     }    
      
   }
   stage('Archival repo') {
    withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
     sh 'mvn package'
     }   
   }
   stage('Docker Build') {
      
   }
   stage('Deploy to Prod') {
      
   }
   
}
