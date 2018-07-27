pipeline {
    agent {
        docker {
            image 'golang:latest'
            args '-p 8091:8181'
        }
    }
    environment {
        GOPATH = "/go:$WORKSPACE"
    }

    stages {
        stage('dep install') {
            steps {
                sh 'curl https://raw.githubusercontent.com/golang/dep/master/install.sh | sh'
                sh './script/addgopath.sh'
            }
        }
        stage('Input') {
            steps {
                input('Do you want to proceed?')
            }
        }

        
        stage("run main") {

            steps {
                sh 'go run ./src/main.go'
            }
        }
        
    }
}