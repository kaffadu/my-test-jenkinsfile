pipeline {
    agent any
    tools {
        terraform 'Terraform'
    }

    stages {
        stage ('checkout') {
            steps {
            checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/kaffadu/my-tf-iac-aws-repo.git']])
            }
        }

        stage ('terraform init') {                              
            steps {
                sh ('terraform init')
                }          
        }
        

        stage ('terraform action') {
            steps {
                echo "Terraform action is --> ${action}"
                sh ('terraform ${action} --auto-approve')
            }
        }
    }
}