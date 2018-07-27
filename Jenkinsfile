pipeline {
    agent {
        docker {
            image 'golang:latest'
            args '-p 8091:8181'
        }
    }

    stages {
        stage('dep install') {
            steps {
                sh 'curl https://raw.githubusercontent.com/golang/dep/master/install.sh | sh'
            }
        }
        
        stage("run main") {
            steps {
                sh 'go run main.go'
            }
        }
        
    }
}