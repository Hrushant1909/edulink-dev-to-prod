pipeline {
    agent any

    stages {
        stage('Backend Build') {
            steps {
                dir('Edulink Backend/EdLink') {
                    sh './mvnw clean package -DskipTests'
                }
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