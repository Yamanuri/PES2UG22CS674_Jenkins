pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'cd main && g++ -o build_output main.cpp'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh 'cd main && chmod +x build_output && ./build_output'
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
