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
  }
  }
    
