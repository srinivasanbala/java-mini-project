pipeline { 
    agent any  
    stages { 
        stage('Build') { 
            steps { 
               sh "mvn package"
               sh "ls -lrt target/"
            }
        }
        stage('Checkout repo proj') {
        steps {
            git branch: 'main',
                credentialsId: 'git',
                url: 'git@github.com:srinivasanbala/terraform.git'

            sh "ls -lrt"
        }
    }
    }
}
