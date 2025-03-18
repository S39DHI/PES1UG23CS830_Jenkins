pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo "Building the C++ program..."
                    sh 'g++ -o hello_exec main/hello.cpp'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo "Running the compiled C++ program..."
                    sh './hello_exec'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo "Deployment Step - Placeholder (Modify as needed)"
                }
            }
        }
    }

    post {
        failure {
            script {
                echo "⚠️ Pipeline failed! Check the logs for errors."
            }
        }
    }
}
