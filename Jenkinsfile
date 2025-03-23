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
          git branch: 'php_server-Proj' , url: 'https://github.com/guptabrijesh760/php_server-Proj.git'
            
        }
    }

    stage('PHPcodeDeploy') { 
        steps{
            sh "sudo cp -r /home/ec2-user/jenkins/phpdevelopment/src/* /var/www/html/"
        }
    }

    stage("Retart Server"){
        steps{
            sh 'systemctl restart httpd'
        }
    }
  }  
}