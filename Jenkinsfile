pipeline {
    agent any
    
    tools {
        terraform 'terraform-test'
    }
    stages {
        stage('git checkout') {
            steps {
                git branch: 'main', credentialsId: '97bbc93c-23bd-4ef3-944b-c55045eaa869', url: 'https://github.com/paritoshtripathy/ec2-terraform.git'
        }
    }
        stage('terraform init'){
            steps {
                sh """
                  terraform init
                """ 
                
            }
        }

        stage('terraform apply'){
            steps {
                sh """
                  terraform destroy -auto-approve
                """ 
                
            }
        }
    }   
}
