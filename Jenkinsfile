// pipeline {
//     agent: any

//     environment {
//         SONAR_SCANNER_HOME = tool 'SonarScanner'
//     }

//     stages {
//         stage ('Checkout') {
//             steps {
//                 git branch: 'main',
//                 credentialsId: 'Jenkins-SonarQube-Docker-Github-PAT',
//                 url: 'https://github.com/Rishab59/Jenkins-SonarQube-Docker.git'
//             }
//         }

//         stage ('SonarQube Analysis') {
//             steps {
//                 withSonarQubeEnv('Sonarqube-Server') {
//                     sh '''
//                         ${SONAR_SCANNER_HOME}/bin/sonar-scanner \
//                         -Dsonar.projectKey=html-app \
//                         -Dsonar.sources= . \
//                         -Dsonar.host.url=http://host.docker.internal:9000
//                     '''
//                 }
//             }
//         }

//         stage ('Build Docker Image') {
//             steps {
//                 sh '''
//                     docker build -t html-app:latest .
//                 '''
//             }
//         }

//         stage ('Deploy Container') {
//             steps {
//                 sh '''
//                     docker stop html-app || true
//                     docker rm html-app || true
//                     docker run -d -p 8085:80 --name html-app-container html-app:latest
//                 '''
//             }
//         }
//     }
// }