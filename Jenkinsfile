pipeline {
  agent {
    docker {
      image 'maven:3.3.9-jdk-8'
      args '-v /home/lasly/.m2'
    }
    
  }
  stages {
    stage('Compile Stage') {
      steps {
        sh '''echo PATH={PATH}
echo M2_HOME={M2_HOME}
mvn clean'''
      }
    }
    stage('Testing Stage') {
      steps {
        sh 'mvn test'
      }
    }
    stage('Deployment Stage') {
      steps {
        sh 'mvn deploy'
      }
    }
  }
}