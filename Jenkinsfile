pipeline {
    agent any

    stages {
        stage('Compile') {
            steps {
                sh "mvn compile"
            }
        }
        stage('Build'){
            steps {
                sh "mvn package"
            }
        }
        stage('Install'){
            steps {
                sh "mvn install"
            }  
        }
        stage('Archive'){
            steps {
                archiveArtifacts 'target/*.jar'
            }
        }
        stage('Fingerprint'){
            steps {
                fingerprint 'target/*.jar'
            }
        }
        stage('Convert XML to HTML'){
            steps {
                junit 'target/surefire-reports/TEST-*.xml'
            }
        } 
     /*  stage('Notify'){
            steps {
                mail bcc: '', body: '''Please check the build "maven project" in Jenkins.

Team Jenkins''', cc: '', from: '', replyTo: '', subject: 'Build has failed.Please check', to: 'sai7devops@gmail.com'
            }
        }*/ 
             
    }

}
