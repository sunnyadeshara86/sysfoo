pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building..'
        sh 'mvn compile'
      }
    }

    stage('Test') {
      steps {
        echo 'Testing..'
        sh 'mvn clean test'
      }
    }

    stage('Package') {
      steps {
        echo 'Deploying....'
        sh 'mvn package -DSkipTests'
        archiveArtifacts '**/target/*.jar'
      }
    }

  }
  tools {
    maven 'Maven 3.9.6'
  }
  post {
    always {
      echo 'This pipeline is completed...'
    }

  }
}