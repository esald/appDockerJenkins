pipeline{
    agent any
    stages{
        stage('build') {
            steps{
                script{
                    app = docker.build("python-app")
                }
            }
        }
        stage('test'){
            steps{
                echo 'Empty'
            }
        }
        stage('deploy'){
            steps{
                script{
                        docker.withRegistry('https://994302838674.dkr.ecr.us-east-1.amazonaws.com/appprueba','ecr:us-east-1:aws-token')
                        app.push("${env.BUILD_NUMBER}")
                        app.push("latest")
                }
            }
        }
    }
}
