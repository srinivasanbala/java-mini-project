pipeline { 
    agent any  
    stages { 
        stage('Build') { 
            steps { 
               sh "ls -lrt "
            }
        }
        stage('Push the artifact to ansible') {
        steps {
            git branch: 'main',
                credentialsId: 'git',
                url: 'git@github.com:srinivasanbala/Ansible.git'

            sh '''
            ls -lrt 
            echo $BUILD_NUMBER
            ls -lrt target/
            cp -pr target/hello-world-?.war roles/tomcat/files/
            ls -lrt roles/tomcat/files/
            '''
        }
    }
    }
}
