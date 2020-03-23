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
        stage('copy to jar file in to deployenvironment'){
            steps {
                sh'scp -o StrictHostKeyChecking=no target/*.jar ubuntu@172.31.44.62:/home/ubuntu'
            }
        }
        stage('run the jar file in deployenvironment'){
            steps {
                sh'ssh -o StrictHostKeyChecking=no ubuntu@172.31.44.62 java -jar /home/ubuntu/*.jar'
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
