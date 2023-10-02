pipeline {
  agent any
  tools {
    maven 'M2_HOME'
        }

  environment {
        AWS_ACCESS_KEY_ID     = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY') 
  } 
  stages {
    stage ('Git Checkout') {
      steps {
        git 'https://github.com/belosheabhijeet/Banking-Final-Project.git'
      }
    }
/*
    stage ('Build Package') {
      steps {
        sh 'mvn clean package' 
  }
}
    stage ('Publish HTML Reports') {
     steps {
       publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: '/var/lib/jenkins/workspace/Banking-Finance-Project/target/surefire-reports', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: '', useWrapperFileDirectly: true])
  }
  }
    stage('Created docker image') {
     steps {
       sh 'docker build -t belosheabhijeet/banking-finance-app:1.0 .'
        }       
         }
    stage('Push the image to dockedr hub') {
     steps {
       withCredentials([usernamePassword(credentialsId: 'docker1-hub', passwordVariable: 'docker_password', usernameVariable: 'docker_user')]) {
     sh 'docker login -u ${docker_user} -p ${docker_password}'
        }
        sh 'docker push belosheabhijeet/banking-finance-app:1.0'
     }
       }
    stage('Deploy the image on the production') {
     steps {
       ansiblePlaybook credentialsId: 'ubuntu-user', disableHostKeyChecking: true, installation: 'ansible', playbook: 'deploy.yml'
           }
}
*/
 stage ('Configure Test-server with Terraform, Ansible and then Deploying'){
            steps {
                dir('my-serverfiles'){
                sh 'sudo chmod 600 abhijeetkeypair.pem'
                sh 'sudo apt-get install terraform'
                sh 'terraform init'
                sh 'terraform validate'
                sh 'terraform apply --auto-approve'
                }
            }
        }
        }
        }
