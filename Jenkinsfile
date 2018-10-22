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
        stage ('Deploy war to GCS') {
            steps {
                googleStorageUpload bucket: 'gs://test1-aidi-demo-post', credentialsId: 'aidi-postdemo', pattern: 'target/*.war'
            }
        }
    }
}
