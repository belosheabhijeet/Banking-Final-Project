pipeline {
  agent any
  tools {
    maven 'M2_HOME'
        }
  stages {
    stage ('Git Checkout') {
      steps {
        git 'https://github.com/belosheabhijeet/Banking-Final-Project.git'
      }
    }
    stage ('Build Package') {
      steps {
        sh 'mvn package' 
  }
}
    stage ('Publish HTML Reports') {
     steps {
       publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: '/var/lib/jenkins/workspace/Banking-Finance-Project/target/surefire-reports', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: '', useWrapperFileDirectly: true])
  }
  }
}
}
