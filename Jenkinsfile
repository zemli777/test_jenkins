pipeline {
    agent any
    triggers { pollSCM('H */4 * * 1-3') }
    stages {
        stage('Build') {
            steps {
                sh 'export GIT_COMMIT=$(git log -1 --format=%h)'
                sh 'docker build -t app:$GIT_COMMIT .'
            }
        }
        stage('Publish master') {
            steps {
                sh 'echo "я закинул это в докер реджистри"'
            }
        }
    }
    post {
        always {
            cleanWs()
            sh 'echo "Очистка чего-ниубдь"'
        }
    }
}