pipeline {
    agent any
    stages {
        stage('Start Grid') {
            steps {
            //sh
                bat "docker-compose up -d hub chrome firefox"
            }
        }
        stage('Run Test') {
            steps {
            //sh
                bat "docker-compose up search-module book-flight-module"
            }
        }
//         stage('Stop Grid') {
//             steps {
//             //sh
//                 bat "docker-compose down"
//             }
//         }

    }
      post {
        always {
            archiveArtifacts artifacts: 'output/**'
             bat "docker-compose down"
        }
    }
}