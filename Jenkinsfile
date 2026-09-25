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
        
        stage('Frontend Build'){
            steps{
                dir('edulink-frontend'){
                    sh 'npm install'
                    sh 'npm run build'
                }
            }
        }

        stage('Archive backend artifacts'){
            steps{
                archiveArtifacts artifacts: '''
                    Edulink Backend/EdLink/target/*.jar,
                    edulink-frontend/dist/**
                ''', fingerprint: true
            }
        }


        stage('Deploy Backend') {
            steps {
                dir('Edulink Backend/EdLink') {
                    sh 'cp target/*.jar /opt/edulink/app.jar'
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