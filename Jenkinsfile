pipeline {
  agent any
  stages  {
    stage('Build') {
      steps {
        echo 'Building..'
      } 
    }
    
    stage('Test') {
      steps {
        parallel(
          "Test": {
            echo 'Tessting..'
          },
          "Integration Test": {
            echo 'Integration Test...'
            
          }
        )
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying....'
      }
    }
  }
}
