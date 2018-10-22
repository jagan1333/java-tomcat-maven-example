pipeline {
    agent any
    stages {
        stage ('Compile Stage') {
            steps {
                withMaven(maven : 'maven') {
                    sh 'mvn clean compile'
                }
            }
        }
        stage ('Testing Stage') {
            steps {
                withMaven(maven : 'maven') {
                    sh 'mvn test'
                }
            }
        } 
        stage ('Package Stage') {
            steps {
                withMaven(maven : 'maven') {
                    sh 'mvn package'
                }
            }
        }
        stage ("Deploy to GCS") {
            steps {
                googleStorageUpload bucket: 'gs://jenkins-pipeline-test', credentialsId: 'archcertificationpro', pattern: 'target/*.war'
            }
        }
    
    }
}
