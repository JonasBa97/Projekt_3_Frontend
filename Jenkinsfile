pipeline {
  agent any

  environment {
    NODE_OPTIONS= "--openssl-legacy-provider"
  }
    
  triggers {
    githubPush()
  }

  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/JonasBa97/Projekt_3_Frontend.git'
      }
    }

    stage('Install Dependencies') {
      steps {
        sh 'npm install'
      }
    }

    stage('Build') {
      steps {
        sh 'npm run build'
      }
    }

    stage('Test') {
      steps {
        echo 'Hier teste ich'
        echo 'Tests erfogreich'
        // sh 'npm test'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Hier deploye ich'
        echo 'Deployment erfolgreich'
        // sh 'deploy-script'
      }
    }
  }

  post {
    success{
      echo 'Pipeline erfogreich'
    }
    failure{
      echo 'Pipeline fehlgeschlagen'
    }
  }
}
