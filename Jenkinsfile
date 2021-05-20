pipeline {
 agent any
 
 stages {

 stage('checkout') {
 steps {
   sh 'ls -ltr /var/lib/jenkins'
 
   }     
 }      
 stage('Set Terraform path') {
   steps {
     script {
        def tfHome = tool name: 'terraform'
        env.PATH = "${tfHome}:${env.PATH}"
        }
    sh 'terraform --version'
        }
    }
  stage ('Provisioning') {
    steps {  
    sh 'cd /var/lib/jenkins/workspace/Terraform && terraform init && terraform plan'
 
   }
  } 
 }
} 
