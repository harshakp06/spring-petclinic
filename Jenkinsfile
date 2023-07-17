pipeline {
  agent any

  tools{
        jdk 'Java17'
        maven 'Maven3'


  }

  stages{
        stage("Cleanup Workspace now "){
            steps {
                cleanWs()
            }

        }
        stage("Build Application"){
            steps {
              script{
                sh "mvn clean package"
                sh "mvn compile"
                sh "mvn package -D maven.test.skip.exec,spring.profiles.active=mysql"
            }
          }   
        }
        stage("Test Application"){
            steps {
                sh "mvn test"
            }

        }
  }     
}

