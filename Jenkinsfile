pipeline {
  agent any
  stages {
    stage('Setup Build Environment'){
      steps {
        sh label: '', script: '''/var/lib/jenkins/workspace/android_app/gradlew --scan -s build'''
      }
    }
    stage('Publish') {
      environment {
        APPCENTER_API_TOKEN = 'aa2813c94f04200c17490d778100427868f28a54'
      }
    steps {
      appCenter apiToken: APPCENTER_API_TOKEN,
              ownerName: 'clanhqjenkins',
              appName: 'clanhq',
              pathToApp: 'testing.apk',
              distributionGroups: 'Testing'
    }
   }
  }
}
