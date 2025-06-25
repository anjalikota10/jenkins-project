pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/anjalikota10/jenkins-project.git'
            }
        }


       

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('sonar') {  
                    sh ''' $SCANNER_HOME/bin/sonar-scanner -Dsonar.projectKey=flaskdemo \
                    -Dsonar.projectName=flaskdemo -Dsonar.java.binaries=target '''
                }    
            }
        }
        
        
    }
