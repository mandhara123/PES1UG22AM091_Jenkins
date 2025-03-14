pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'g++ -o pes1ug22am091-1 main.cpp'  // Compile C++ file
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh './abcd'  // Run the compiled file
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline Failed'
        }
    }
}
