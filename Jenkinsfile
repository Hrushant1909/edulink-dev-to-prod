pipeline {
    agent any

    stages {
        stage('Check Project Structure') {
            steps {
                sh '''
                    echo "Current directory:"
                    pwd

                    echo "Repository structure:"
                    find . -maxdepth 4 -type f | sort
                '''
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed!'
        }
    }
}