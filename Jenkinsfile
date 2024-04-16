pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'compiling the code for sysfoo app'
        sh 'mvn compile'
      }
    }

    stage('test') {
      steps {
        echo 'unit tests'
        sh 'mvn clean test'
      }
    }

    stage('package') {
      steps {
        echo 'generating artificat'
        sh 'mvn package -DskipTests'
        archiveArtifacts 'target/*.war'
      }
    }

  }
  tools {
    maven 'Maven 3.6.3'
  }
  post {
    always {
      echo 'This pipeline is completed..'
    }

  }
}