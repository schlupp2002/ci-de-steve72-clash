pipeline {
    agent { docker { image 'node:10.15.1' } }
    environment { HOME="." }
    stages {
        stage('Build') {
            steps {
                
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                echo 'Building..'
                sh 'npm install'
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