pipeline {
    agent any
    stages {

        stage('Checkout Codebase') {
            steps {
            checkout scm: [$class: 'GitSCM',
            userRemoteConfigs: [[branch: 'main', credentialsId: 'git-jenking-ssh',url: 'git@github.com:criferna/EjemploCurso.git']]]

            }
        }
        stage('Build') {
            steps {
                sh './test.sh'

            }
        }
        stage('Test') {
            steps {
                sh './test.sh'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo Done!'
            }
        }
    }
}
