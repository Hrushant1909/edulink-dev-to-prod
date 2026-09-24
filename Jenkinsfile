pipeline{
    agent any


    stages{


        stage('Backend Build'){
            steps{
                dir('EdLink'){
                    sh './mvnw clean package -DskipTests'
                }
            }
        }


        

    }
}