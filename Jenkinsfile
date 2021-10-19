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
                sh 'ssh -p7413 hub@5.189.159.78 git -C /home/hub/cicd.hub-secure.com pull'
            }
        }
        stage('Check website is up') {
            steps {
                echo 'Check website is up'
                sh 'curl -Is 5.189.159.78 | head -n 1'
            }
        }
    }
}
