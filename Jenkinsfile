pipeline { 
    agent any  
    stages { 
        stage('Build') { 
            steps { 
               sh "mvn package"
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
            cp -pr target/hello-world-?.war roles/tomcat/files/hello-word-$BUILD_NUMBER.war
            ls -lrt roles/tomcat/files/
            git add --all
            git commit -am "added latest artifcat $BUILD_NUMBER"
            git push
            '''
        }
    }
    }
}
