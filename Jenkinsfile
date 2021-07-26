pipeline {
    environment {
        registry = 'sahana1212/jenkinsdatascience'
        registryCredential = 'sahana1212'
        dockerImage = 'jenkinsdata'
        imagename = 'Dockerfile'
    }
    agent any
    stages {
//         stage('Build Docker Image') {
//             agent any
//             steps {
//                 script {
//                     dockerImage = docker.build registry + ":$BUILD_NUMBER"
//                 }
//             }
//         }
           stage('Building image') {
               agent any
               steps{
                   sh """
                     docker build -t ${dockerImage} .
                     docker tag ${dockerImage} ${dockerImage}:latest
                     docker push ${dockerImage}:latest
               }
           }
//         stage('Push Docker Image to Registry') {
//             agent any
//             steps {
//                 script {
//                     docker.withRegistry('',registryCredential) {
//                         dockerImage.push()
//                     }
//                 }
//             }
//         }
//         stage('Remove Unused docker image') {
//             steps {
//                 sh "docker rmi $registry:$BUILD_NUMBER"
//             }
//         }
    }
}
