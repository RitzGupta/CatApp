pipeline{
    stage('SCM Checkout'){
        git branch: 'main', url: 'https://github.com/RitzGupta/CatApp.git'
    }
    stage('Build Docker Image'){
        sh 'docker build -t catapp .'
    }

    stage('Push Docker Image to ECR'){
        // Loging to ECR
        sh 'aws ecr get-login-password --region ap-south-1 | docker login --username RitikGupta --password-stdin 671394177905.dkr.ecr.ap-south-1.amazonaws.com'
        // Tag Image
        sh 'docker tag catapp:latest 671394177905.dkr.ecr.ap-south-1.amazonaws.com/catapp:latest'
        // Push Image
        sh 'docker push 671394177905.dkr.ecr.ap-south-1.amazonaws.com/catapp:latest'

    }
    stage('Create EKS Deployment & Service'){
        sh 'echo "Hello" '

    }


}