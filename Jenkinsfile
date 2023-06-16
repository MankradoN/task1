pipeline {
    agent any

    stages {
        stage('set-up'){
            steps{
                sh 'docker rm -f $(docker ps -aq) || true'
            }
        }

        stage('build docker image'){
            steps{
                sh 'docker build -t mankradon/python .'
            }
        }

        stage('run docker') {
            steps {
                sh "docker run -d -p 80:5500 --name flask-app mankradon/python"
            }
        }
    }
}
