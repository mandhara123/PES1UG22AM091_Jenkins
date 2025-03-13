pipeline {
    agent any

    environment {
        SRN = 'pes1ug22am091'
    }

    stages {

        stage('Build') {
            steps {
                echo 'Starting Build Stage...'
                sh 'g++ -o ${SRN} main.cpp'
                echo 'Build completed: ${SRN}'
            }
        }

        stage('Test') {
            steps {
                echo 'Starting Test Stage...'
                sh './${SRN}'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying Application...'
                sh 'echo "Deployment successful for ${SRN}"'
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
