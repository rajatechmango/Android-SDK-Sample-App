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
        APPCENTER_API_TOKEN = '1aa666d8324c7e92ad1963a22c6a8fcb5faf1c50'
      }
    steps {
      appCenter apiToken: APPCENTER_API_TOKEN,
              ownerName: 'clanhqjenkins-gmail.com',
              appName: 'clanhq',
              pathToApp: 'testing.apk',
              distributionGroups: 'casey, niccoli'
    }
   }
  }
}
