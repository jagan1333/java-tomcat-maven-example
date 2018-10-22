pipeline {
  agent any
  stages {
    stage('compile') {
      steps {
        withMaven(globalMavenSettingsConfig: 'maven', jdk: 'java1.8', maven: 'maven', mavenOpts: 'mvn clean compile')
      }
    }
    stage('print') {
      steps {
        echo 'Hello'
      }
    }
  }
}