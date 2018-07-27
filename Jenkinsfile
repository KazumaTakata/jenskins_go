pipeline {
    agent {
        docker {
            image 'golang:latest'
            args '-p 8080:8181'
        }
    }

    stages {
        stage('dep install') {
            steps {
                sh 'curl https://raw.githubusercontent.com/golang/dep/master/install.sh | sh'
            }
        }
        
    }
}