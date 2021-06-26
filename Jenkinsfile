pipeline {

  environment {
    registry = "happyit/myweb"
    dockerImage = ""
//    imagename = "yenigul/hacicenkins"
    registryCredential = 'dockerhub'
  }

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/hieunt84/cicd-jenkins-k8s.git'
      }
    }

    stage('Build image') {
      steps{
        script {
          dockerImage = docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }

    stage('Push Image') {
      steps{
        script {
          docker.withRegistry( "", registryCredential ) {
            dockerImage.push()
          }
        }
      }
    }

//    stage('Deploy App') {
//      steps {
//        script {
//          kubernetesDeploy(configs: "myweb.yaml", kubeconfigId: "mykubeconfig")
//        }
//      }
//    }

  }

}
