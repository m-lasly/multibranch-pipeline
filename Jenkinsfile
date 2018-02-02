pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven() {
                     sh "mvn clean install"
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven() {
                    sh 'mvn test'
                   
                }
            }
        }
    }
          
   post {
      always {
        junit '**/target/surefire-reports/*.xml'
      }
   } 
}