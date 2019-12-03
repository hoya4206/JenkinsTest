pipeline {
  agent any
  stages {
    stage('Initialize') {
      steps {
        sh 'chmod +x gradlew'
      }
    }

    stage('build') {
      steps {
        sh './gradlew build'
      }
    }

  }
}