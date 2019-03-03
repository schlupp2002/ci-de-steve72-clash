pipeline {
    agent { docker { image 'node:10.15.1' } }
    environment { HOME="." }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                sh 'npm install'
                sh 'ng build --prod --aot'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'ng test --code-coverage'
                sh 'ng test --single-run'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}