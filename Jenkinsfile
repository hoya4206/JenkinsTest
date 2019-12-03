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
        sh '''json=\'{"parameter": [{"name": "forceUpdate", "value": true},
  {"name":"fileParam", "file":"file0"}]}\'

url=http://192.168.0.121:6061/upload

curl -v $url -F file0=@/var/jenkins_home/workspace/JenkinsTest_master/app/build/outputs/apk/debug$app-debug.apk -F json="$json" --user username:password'''
      }
    }

  }
}