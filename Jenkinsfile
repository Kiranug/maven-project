pipeline {
    agent any
    
     parameters { 
         string(name: 'Staging', defaultValue: '3.88.60.27', description: 'Staging Server')
         string(name: 'tomcat_prod', defaultValue: '34.209.233.6', description: 'Production Server')
    } 

    stages {
        stage('SCM checkout') {
            steps {
               git 'https://github.com/Kiranug/maven-project.git'
          }
        }
         stage('Build') {
            steps {
                echo 'Building..'
                sh 'mvn clean package'
            }
             post {
                 success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                 }
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
