pipeline {
  agent any
  stages {
    stage('Initialize') {
      steps {
        sh 'ls -al'
      }
    }

    stage('build') {
      steps {
        sh '''chmod +x gradlew;
./gradlew build --stackstrace'''
      }
    }

  }
}