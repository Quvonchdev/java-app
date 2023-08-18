pipeline{
    agent any
    stages{
        stage("soner quality chek"){
            agent {
                docker {
                    iamge 'openjdk:11'
                }
            }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-token') {
                        sh 'chmod +x gradlew'
                        sh './gradlew sonarqube'
                    }

                }
            }

        }
    }
}