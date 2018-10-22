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
        stage ('Deploy to Tomact') {
            steps {
                sh 'cp /Users/Shared/Jenkins/Home/workspace/mvn_pipeline/target/*.war /Users/jagannath.s/Documents/apache-tomcat-8.5.34/webapps/'
            }
        }
    
    }
}
