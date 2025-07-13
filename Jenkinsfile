pipeline {
  agent any
  stages {
    stage('Clone Repo') {
      steps {
        echo 'Cloning repo...'
        git 'https://github.com/vishuanjali/jenkins-handson.git'
      }
    }

    stage('Install Dependencies') {
      steps {
        echo 'Installing dependencies...'
        sh 'npm install'
      }
    }

    stage('Docker Build') {
      steps {
        echo 'Building Docker image...'
        sh 'docker build -t jenkins-node-app .'
      }
    }

    stage('Docker Run') {
      steps {
        echo 'Running Docker container...'
        sh 'docker run -d -p 3000:3000 jenkins-node-app'
      }
    }
  }
}

