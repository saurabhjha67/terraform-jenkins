pipeline {
 agent any
 
 stages {
      
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
    sh 'terraform init'
     sh 'terraform plan -var "name=$(name)"'
 
   }
  } 
 }
} 
