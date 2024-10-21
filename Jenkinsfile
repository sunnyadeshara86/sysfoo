pipeline {
    agent any

    tools {
      maven 'Maven 3.9.6'
    }
    
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
            }
        }
    }

    post {
      always {
        echo 'This pipeline is completed...'
      }
    }
}
