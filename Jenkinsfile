pipeline {
    
    
    agent any
	

    stages {
        
        stages {
        stage('Code checkout') {
            steps{
            git credentialsId: 'git-cred-repo-priv', url: 'https://github.com/Nitinda97/project-aks-terraform.git'
            }
        }
		
        stage('TF Init&Plan') {
        steps {
          dir("terraform"){
          sh 'terraform init'
          sh 'terraform plan'
	}
        }      
      }

      stage('TF Apply') {
        steps {
	  dir("terraform")
	{
          sh 'terraform apply --auto-approve'
        }
        }
       }
        
	}}
