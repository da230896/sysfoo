pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'Compiling sysfoo app'
        sh 'mvn compile'
      }
    }

    stage('test') {
      steps {
        echo 'Testing sysfoo app'
        sh 'mvn clean test'
      }
    }

    stage('package') {
      steps {
        echo 'Packaging sysfoo app'
        sh 'mvn package -DskipTests'
        archiveArtifacts 'target/*.war'
      }
    }

  }
  tools {
    maven '3.6.3'
  }
}