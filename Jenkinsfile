pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                script {
                    git(
                        branch: 'master',
                        url: 'https://github.com/Liquiditee123/jenkins-git-integration.git'
                    )
                }
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }  // <-- Fixed: Closed the 'stages' block properly
    post {
        success {
            echo ':white_tick: Build and Tests Successful!'
        }
        failure {
            echo ':x: Build Failed! Check logs for issues.'
        }
    }
}
