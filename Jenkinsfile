pipeline {
    agent any

    environment {
        AWS_DEFAULT_REGION = 'us-east-1'
    }

    stages {

        stage('Clone Repository') {
            steps {
                echo 'Cloning Repository...'
                git branch: 'main',
                    url: 'https://github.com/raghulpalanikumar/Lab-1'
            }
        }

        stage('Terraform Init') {
            steps {
                echo 'Initializing Terraform...'
                sh 'terraform init'
            }
        }

        stage('Terraform Plan') {
            steps {
                echo 'Planning Infrastructure...'
                sh 'terraform plan -var="ami_id=ami-0b6c6ebed2801a5cb"'
            }
        }

        stage('Terraform Apply') {
            steps {
                echo 'Applying Infrastructure...'
                sh 'terraform apply -auto-approve -var="ami_id=ami-0b6c6ebed2801a5cb"'
            }
        }
    }
}
