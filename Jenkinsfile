pipeline {
    agent any

    environment {
        SRN = 'PES1UG22AM091'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Starting Build Stage...'
                sh 'g++ -o ${SRN}-1 main.cpp'
                echo 'Build completed: ${SRN}-1'
            }
        }

        stage('Test') {
            steps {
                echo 'Starting Test Stage...'
                sh './${SRN}-1'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying Application...'
                sh 'echo "Deployment successful for ${SRN}-1"'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
        success {
            echo 'Pipeline completed successfully'
        }
    }
}
