pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID     = credentials('toksmajek')
        AWS_SECRET_ACCESS_KEY = credentials('aws-secret-access-key')
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Toksmajek/terraform-project.git'
            }
        }
        stage('Terraform install') {
            steps {
                sh 'snap install terraform --classic'
            }
        }
         stage('Terraform Init') {
            steps {
                sh 'terraform init'
            }
        }
        stage('Terraform Plan') {
            steps {
                sh 'terraform plan '
            }
        }
        stage('Terraform Apply') {
            steps {
                sh 'terraform apply -auto-approve '
            }
        }
    }
}
