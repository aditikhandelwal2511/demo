pipeline {
  agent any
  stages  {
    stage('Build') {
      steps {
        echo 'Buiilding..'
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
  }
   post {
        success{
            office365ConnectorSend message: "Build status ", status:"Sucess", webhookUrl:'https://capgemini.webhook.office.com/webhookb2/5891a8da-e48d-49f2-9223-ee31054cca37@76a2ae5a-9f00-4f6b-95ed-5d33d77c4d61/JenkinsCI/6b738c9560514c5b9b0f628ec14b0340/5392d4d3-9c22-42b8-ba33-c5b98e05612e'
        }
        failure{
                       office365ConnectorSend message: "Build status ", status:"Failed", webhookUrl:'https://capgemini.webhook.office.com/webhookb2/5891a8da-e48d-49f2-9223-ee31054cca37@76a2ae5a-9f00-4f6b-95ed-5d33d77c4d61/JenkinsCI/6b738c9560514c5b9b0f628ec14b0340/5392d4d3-9c22-42b8-ba33-c5b98e05612e'

        }
}
}
