pipeline {
    agent any

options {
  buildDiscarder logRotator(daysToKeepStr: '1', numToKeepStr: '1')
}

    stages {
        stage('Clean') {
            steps {
                sh "mvn clean"
            }
        }
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
        stage (Email Notification'){
            steps {
                mail bcc: '', body: 'Hi welocme to Jenkins alerts', cc: '', from: '', replyTo: '', subject: '', to: 'sai7devops@gmail.com'
          }

        }
       /* stage('Build docker image'){
            steps {
                sh "docker build -t reddemma/image:2.0.0"
            }  
        }
        stage('Push  docker image'){
            steps {
                withCredentials([string(credentialsId: 'dockerpwd', variable: 'DockerHubPWD')]) {
                sh "docker login -u reddemm -p ${DockerHubPWD}"
            }
                sh "docker build -t reddemma/image:2.0.0"
            }  
        }


        stage('Deploy'){
            steps {
                sh "mvn deploy"
            }  
        }*/

       /* stage('Archive'){
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
        stage('copy to jar file in to devenvironment'){
            steps {
                sh 'scp -o StrictHostKeyChecking=no target/*.jar ubuntu@172.31.44.62:/home/ubuntu'
            }
        }
        stage('run the jar file in devenvironment'){
            steps {
                sh 'ssh -o StrictHostKeyChecking=no ubuntu@172.31.44.62 java -jar /home/ubuntu/*.jar'
            }
        } 
   
        stage('Notify'){
            steps {
                mail bcc: '', body: '''Please check the build "maven project" in Jenkins.

Team Jenkins''', cc: '', from: '', replyTo: '', subject: 'Build has failed.Please check', to: 'sai7devops@gmail.com'
            }
        }*/ 
             
    }

}
