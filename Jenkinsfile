pipeline {
  agent any
  stages {
   //# stage ('Build Artifact - Maven'){
    //#  steps{
     //#   sh "/usr/local/apache-maven-3.9.3 mvn clean package -DskipTests=true"
      //#//  # archive 'target/*.jar'
      //#} 
    //#}
    stage('SonarQube analysis') {
      steps{
        withSonarQubeEnv(credentialsId: 'sonarcloud') { // You can override the credential to be used
          sh "mvn verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -D sonar.projectKey=harshakp06_spring-petclinic,spring.profiles.active=mysql"

        }
      }
    }
  }
}
