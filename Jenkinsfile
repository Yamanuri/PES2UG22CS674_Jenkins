pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    sh '''
                        echo "Current workspace: $(pwd)"
                        ls -la  # Debugging: List files in the workspace
                        g++ -o build_output main.cpp
                    '''
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh '''
                        chmod +x build_output
                        ./build_output
                    '''
                }
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying the application..."
            }
        }
    }

    post {
        failure {
            echo "Pipeline failed"
        }
    }
}
