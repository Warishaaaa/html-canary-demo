pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/Warishaaaa/html-canary-demo.git'
            }
        }

        stage('Stop Old Server') {
            steps {
                sh 'fuser -k 5000/tcp || true'
            }
        }

        stage('Start V1 Server') {
            steps {
                sh "nohup python3 -m http.server 5000 --directory . > v1.log 2>&1 &"
            }
        }
    }
}
