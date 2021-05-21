// Comments for webhook test
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
    echo '${name}'
    sh 'terraform init'
     sh 'terraform plan -state=${name}.tfstate -var name=${name}'
    sh 'terraform apply -state=${name}.tfstate -var name=${name} -auto-approve'
   }
  } 
 }
} 
