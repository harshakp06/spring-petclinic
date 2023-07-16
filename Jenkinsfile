pipeline {
  agent any
  environment {
    SONARCLD = credentials('sonarqube')
  }
  stages {
    stage ('sonarcloud'){
      steps{
        script{
          env.SONAR_TOKEN = "${SONARCLD}"
          sh "mvn verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -D sonar.projectKey=harshakp06_spring-petclinic,spring.profiles.active=mysql"

          
        }
      }
    }
    
   //# stage ('Build Artifact - Maven'){
    //#  steps{
     //#   sh "/usr/local/apache-maven-3.9.3 mvn clean package -DskipTests=true"
      //#//  # archive 'target/*.jar'
      //#} 
    //#}
   // stage('SonarQube analysis') {
     // steps{
       // withSonarQubeEnv('My SonarQube Server', envOnly: true) {
                                // This expands the evironment variables SONAR_CONFIG_NAME, SONAR_HOST_URL, SONAR_AUTH_TOKEN that can be used by any script.
         //          println ${env.SONAR_HOST_URL} 
           //     }
      //}
   // }  

   //stage('SonarQube analysis - 2') {
     // steps{
       // withSonarQubeEnv(credentialsId: 'sonarcloud') { // You can override the credential to be used
         // sh "mvn verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -D sonar.projectKey=harshakp06_spring-petclinic,spring.profiles.active=mysql"

  //      }
    //  }
  //  }
  }
}
