pipeline {
  agent {
    docker {
      image 'maven:3.6.3-jdk-11'
    }

  }
  stages {
    stage('Compile') {
      steps {
        sh 'mvn compile'
      }
    }

    stage('Packaging') {
      steps {
        sh 'mvn install -DskipTests'
      }
    }

    stage('Archiving artifacts') {
      steps {
        archiveArtifacts 'target/*'
      }
    }

  }
}