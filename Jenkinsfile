pipeline {
  agent any

  environment {
    IMAGE = 'devkhuman3/website:latest'
  }

  stages {
    stage('Clone') {
      steps {
        git 'https://github.com/Devkhuman/website.git'
      }
    }

    stage('Build Docker Image') {
      steps {
        sh 'docker build -t $IMAGE .'
      }
    }

    stage('Push to DockerHub') {
      steps {
        withDockerRegistry([credentialsId: 'dockerhub-creds', url: '']) {
          sh 'docker push $IMAGE'
        }
      }
    }

    stage('Deploy to K8s') {
      steps {
        sh 'kubectl apply -f k8s-deployment.yaml'
      }
    }
  }
}
