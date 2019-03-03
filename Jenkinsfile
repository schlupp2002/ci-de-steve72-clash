pipeline {
    agent { docker { image 'node:10.15.1' } }
    environment { HOME="." }
    stages {
        stage('Build') {
            steps {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
            }
            steps {
                echo 'install node modules'
                sh 'npm install'
            }
            steps {
                sh 'ng build --prod --aot'
            }
        }
        stage('Test') {
            steps {
                echo 'Code coverage'
                sh 'ng test --code-coverage'
            }
            steps {
                echo 'Testing..'
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