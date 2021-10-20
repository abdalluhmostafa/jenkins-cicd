pipeline {
    agent any 
    stages {
        stage('Clone the repo') {
            steps {
                echo 'clone the repo'
                sh 'rm -fr jenkins-cicd'
                sh 'git clone https://github.com/abdalluhmostafa/jenkins-cicd.git'
            }
        }
        stage('push repo to remote host') {
            steps {
                echo 'connect to remote host and pull down the latest version'
                sh 'ssh -pPOPRT USER@IP "cd /var/www/html; git pull"'
		sh 'cat hello'
            }
        }
        stage('Check website is up') {
            steps {
                echo 'Check website is up'
                sh 'curl -Is test.com | head -n 1'
            }
        }
    }
}
