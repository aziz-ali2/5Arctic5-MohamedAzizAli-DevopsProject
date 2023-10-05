pipeline {
    agent any

    stages {
        stage('git') {
            steps {
                git branch: 'MohamedAzizALI-5ARCTIC5', credentialsId: 'git_cred', url: 'https://github.com/aziz-ali2/5Arctic5-MohamedAzizAli-DevopsProject.git'
            }
        }
        stage('clean') {
          steps {
            sh 'mvn clean'
          }
        }
        stage('build') {
          steps {
            sh 'mvn compile'
          }
        }
        stage('Package') {
          steps {
            sh 'mvn package -DskipTests'
          }
        }
    }

    post {
        failure {
            emailext attachLog: true, body: 'Error', subject: 'Pipeline failed', to: 'mohamedaziz.ali@esprit.tn'
        }
    }
}
