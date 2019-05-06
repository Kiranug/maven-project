pipeline {
    agent any

    stages {
        stage('SCM checkout') {
            steps {
               git 'https://github.com/Kiranug/maven-project.git'
          }
        }
         stage('Build') {
            steps {
                echo 'Building..'
                sh 'mvn package'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
