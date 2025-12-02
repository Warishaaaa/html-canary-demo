pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                sh 'git clone --depth 1 https://github.com/YOUR-USERNAME/html-canary-demo.git .'
            }
        }

        stage('Stop Old Server') {
            steps {
                sh 'pkill -f "http.server 5000" || true'
            }
        }

        stage('Start V1 Server') {
            steps {
                sh 'python3 -m http.server 5000 --directory . >/dev/null 2>&1 &'
            }
        }
    }
}
