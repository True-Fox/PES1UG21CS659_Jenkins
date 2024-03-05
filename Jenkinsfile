pipeline{
    agent any
    stages{
        stage('Clone repository'){
            steps {
                checkout([$class: 'GitSCM',
                branches: [[name: '*/main']],
                userRemoteConfigs: [[url: 'https://github.com/True-Fox/PES1UG21CS659_Jenkins/']]])
            }
        }

        stage('Build'){
            steps{
                build 'PES1UG21CS659-1'
                sh 'g++ ./main/main.cpp -o output'
            }
        }

        stage('Test'){
            steps{
                sh './output'
            }
        }

        stage('Deploy'){
            steps{
                echo 'deploy'
            }
        }

        post{
            failure{
                error 'Pipeline failed'
            }
        }
    }
}