pipeline {
  agent any

  tools{
        jdk 'Java17'
        maven 'Maven3'


  }

  stages{
        stage("Cleanup Workspace  now only"){
            steps {
                cleanWs()
            }

        }
        stage("Build Application"){
            steps {
                sh "mvn clean package"
            }

        }
        stage("Test Application"){
            steps {
                sh "mvn test"
            }

        }
        

 


}

