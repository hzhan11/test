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
        fileExists 'app\\build\\outputs\\apk\\debug\\app-debug.apk'
        bat 'adb install app\\build\\outputs\\apk\\debug\\app-debug.apk'
      }
    }

    stage('test') {
      steps {
        echo 'start test'
        bat 'adb shell am instrument -w -r    -e debug false -e class \'com.example.myapplication.ExampleInstrumentedTest\' com.example.myapplication.test/androidx.test.runner.AndroidJUnitRunner'
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
        bat 'adb uninstall com.example.myapplication'
      }
    }

  }
}