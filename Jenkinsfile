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
./gradlew build --stacktrace'''
      }
    }

    stage('upload') {
      steps {
        sh ' curl -i -X POST -H "Content-Type: multipart/form-data" -F "apk=@/var/jenkins_home/workspace/JenkinsTest_master/app/build/outputs/apk/debug/app-debug.apk" -F "forceUpdate=true" http://192.168.0.121:6061/upload/'
      }
    }

  }
}