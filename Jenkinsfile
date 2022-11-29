pipeline { 
    agent any  
    stages { 
        stage('Build') { 
            steps { 
               mvn package
               ls -lrt target/
            }
        }
    }
}
