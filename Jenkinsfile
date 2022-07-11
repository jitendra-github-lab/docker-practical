library identifier: 'shared-lib-demo@main', retriever: modernSCM(
[$class: 'GitSCMSource',
remote: 'https://github.com/jitendra-github-lab/shared-lib.git'])

pipeline {
    agent any
    
    environment{
        PATH = "/usr/local/bin:${env.PATH}"
    }
    
    stages {
        stage('dev-build') {
            steps {
                output = checkoutrepo.checkoutRepo 'https://github.com/jitendra-github-lab/docker-practical.git'
                echo "OUTPUT : ${output}"
            }
        }      
    }
}
