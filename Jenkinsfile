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
        stage('Archive backend artifacts'){
            steps{
                archiveArtifacts artifacts: 'Edulink Backend/EdLink/target/*.jar', fingerprint: true
            }
        }


        stage('Frontend Build'){
            steps{
                dir('edulink-frontend'){
                    sh 'npm install'
                    sh 'npm run build'
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