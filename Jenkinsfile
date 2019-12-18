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
        APPCENTER_API_TOKEN = credentials('at-this-moment-you-should-be-with-us')
      }
    steps {
      appCenter apiToken: APPCENTER_API_TOKEN,
              ownerName: 'janes-addiction',
              appName: 'ritual-de-lo-habitual',
              pathToApp: 'three/days/xiola.apk',
              distributionGroups: 'testing'
    }
   }
  }
}
