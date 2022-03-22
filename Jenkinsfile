pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building..'
      }
      
    }
    stage('Test') {
      steps {
        parallel(
          "Test": {
            echo 'Testing..'
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
    stage('archival') {
step([$class: 'JUnitResultArchiver', allowEmptyResults: true, testResults: 'target\\surefire-reports\\TEST-*.xml'])
archiveArtifacts allowEmptyArchive: true, artifacts: 'target\\*.jar', followSymlinks: false, onlyIfSuccessful: true
}
  }
}
