pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                branches: [[name: '*/main']],
                userRemoteConfigs: [[url: 'git@github.com:S39DHI/PES1UG23CS830_Jenkins.git']]])
            }
        }

        stage('Build') {
            steps {
                script {
                    echo "🛠️ [PES1UG23CS830] Compiling C++ program..."
                    sh 'g++ main/hello.cpp -o output'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo "✅ [PES1UG23CS830] Running the compiled program..."
                    sh 'chmod +x output'
                    sh './output'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo "🚀 [PES1UG23CS830] Deployment Step - Modify as needed"
                }
            }
        }
    }

    post {
        failure {
            script {
                echo "❌ [PES1UG23CS830] Pipeline failed! Check logs for errors."
            }
        }
    }
}
