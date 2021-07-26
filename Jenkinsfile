pipeline {
    environment {
        registry = 'sahana1212/jenkinsdatascience'
        registryCredential = 'sahana1212'
        dockerImage = 'jenkinsdata'
        imagename = 'Dockerfile'
    }
    agent any
    stages {
           stage('Building image') {
               agent any
               steps{
                   sh """
                     docker build -t ${dockerImage} .
                     docker tag ${dockerImage} ${dockerImage}:latest
                     docker push ${dockerImage}:latest
                    """
               }
           }
     }
}
