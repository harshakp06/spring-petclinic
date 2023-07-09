pipeline {
  agent any
  stages {
    stage ('Build Artifact - Maven'){
      steps{
        sh "/usr/local/apache-maven-3.9.3 mvn clean package -DskipTests=true"
      //  # archive 'target/*.jar'
      } 
    }
    stage('SonarQube analysis') {
      steps{
        withSonarQubeEnv(credentialsId: 'sonarcloud', installationName: 'My SonarQube Server') { // You can override the credential to be used
          sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.*.*.*:sonar'

        }
      }
    }
  }
}
