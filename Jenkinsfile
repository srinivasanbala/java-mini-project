pipeline { 
    agent any  
    stages { 
        stage('Build') { 
            steps { 
               sh "mvn package"
               sh "ls -lrt target/"
            }
        }
        stage('Push the artifact to ansible') {
        steps {
            git branch: 'main',
                credentialsId: 'git',
                url: 'git@github.com:srinivasanbala/Ansible.git'

            sh '''
            ls -lrt 
            ls -lrt target/
        }
    }
    }
}
