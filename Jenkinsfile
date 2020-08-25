pipeline {
  agent any
  stages {
    stage('build') {
      environment {
        ANDROID_SDK_ROOT = 'C:\\Users\\xjtu_\\AppData\\Local\\Android\\Sdk'
      }
      steps {
        echo 'start to build'
        bat 'dir'
        bat 'gradlew.bat build'
      }
    }

    stage('install') {
      steps {
        bat 'adb install'
        fileExists '1.apk'
      }
    }

    stage('test') {
      steps {
        echo 'start test'
      }
    }

    stage('report') {
      steps {
        echo 'start reporting'
      }
    }

    stage('clean') {
      steps {
        echo 'clean environment'
      }
    }

  }
}