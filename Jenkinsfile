pipeline {
    agent any
    stages {

        stage('Descarga del código') {
            steps {
            checkout scm: [$class: 'GitSCM',
            branches: [[name: '*/main']],
            userRemoteConfigs: [[credentialsId: 'git-jenking-ssh',url: 'git@github.com:criferna/EjemploCurso.git']]]
            }
        }
        stage('Compilar') {
            steps {
                sh 'chmod +x test.sh'
                sh './test.sh'
            }
        }
        stage('Probar') {
            steps {
                sh './test.sh'
            }
        }
        stage('Prueba exitosa?') {
            steps {
                input "¿Se realizó la prueba exitosamente?"
                sh 'echo Done!'
            }
        }
    }
}
