pipeline {
    agent any
    environment {
        // Define any environment variables here
    }
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out repository...'
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Building the project...'
                // Add your build commands here (e.g., for Maven, Gradle, or npm)
                sh './gradlew build' // Example for Gradle
                // sh 'mvn clean package' // Example for Maven
                // sh 'npm install' // Example for Node.js
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                // Add your test commands here
                sh './gradlew test' // Example for Gradle
                // sh 'mvn test' // Example for Maven
                // sh 'npm test' // Example for Node.js
            }
        }
        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                echo 'Deploying application...'
                // Add your deployment commands here (e.g., Docker, Kubernetes, SCP, etc.)
                // sh 'scp target/*.jar user@server:/deploy/path/'  // Example
                // sh 'kubectl apply -f deployment.yaml'  // Example for Kubernetes
            }
        }
    }
    post {
        always {
            echo 'Pipeline completed!'
        }
        success {
            echo 'Pipeline finished successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}







