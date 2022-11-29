pipeline { 
    agent any  
    stages { 
        stage('Build') { 
            steps { 
               sh "mvn package"
               sh "ls -lrt target/"
            }
        }
        stage('Git clone'){
           steps{
             script{
                 GIT_CREDS = credentials(git)
                 sh '''
                    git clone git@github.com:srinivasanbala/terraform.git
                    ls -lrt
                  '''
                  }
             }
          }
    }
}
