pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                // Removed the semicolon at the end of the URL
                git branch: 'main', url: 'https://github.com/245123737080-pixel/calculator.git';
            }
        }

        stage('Compile') {
            steps {
                sh 'javac calculator.java'
            }
        }

        stage('Build & Run') {
            steps {
                // Using echo to label the output in the console
                echo "Running calculation test..."
                sh 'java calculator 25 5'
            }
        }

        stage('Test') {
            steps {
                sh 'java calculator 30 -5'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment completed'
            }
        }
    }
    
    post {
        always {
            echo 'Pipeline execution finished.'
        }
        success {
            echo 'Build was successful!'
        }
        failure {
            echo 'Build failed. Check the console output.'
        }
    }
}
   }
}
