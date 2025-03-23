pipeline { 
  agent {
    // using agent manchine call by label  
    label 'phpdev' 
  }
  options {
    // Timeout counter starts AFTER agent is allocated
    timeout(time: 60, unit: 'SECONDS')
  } 
  environment { 
    CONTAINERIMAGE = 'ngnix:latest'
    }

  stages {
    stage("CodeCheckout"){
        steps{
            
        }
    }

    stage('KillOldContainer') { 
        steps{
            sh 'docker rm -f serverci1'
        }
    }

    stage("BuildContainer"){
        steps{
            sh 'docker run -dit --name serverci1 $CONTAINERIMAGE'
        }
    }
  }  
}