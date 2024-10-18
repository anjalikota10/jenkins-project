pipeline {
    agent any
    stages {
        stage('git checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/anjalikota10/jenkins-project.git'
            }
        }

        stage('Build & Tag docker image') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker-creds', toolName: 'docker') {
                      sh 'docker build -t devops830/python-app:latest .'
                    } 
                }
            }
        }

        stage('Push docker image') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker-creds', toolName: 'docker') {
                        sh 'docker push devops830/python-app:latest'
                    }
                }
            }
        }
        






    }
}

