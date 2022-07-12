git_url = credentials('shared_lib')
library identifier: 'shared-lib-demo@main', retriever: modernSCM(
[$class: 'GitSCMSource',
 remote: "${git_url}"])

pipeline {
    agent any
    
    environment{
        PATH = "/usr/local/bin:${env.PATH}"
    }
    
    stages {
        stage('dev-build') {
            steps {
                script{
                 value = credentials('shared_lib')
                 echo "CRED : ${value}"
                 sh "rm -r docker-practical"
                 output = checkoutrepo.checkoutRepo 'https://github.com/jitendra-github-lab/docker-practical.git'
                 echo "OUTPUT : ${output}"                    
                }
            }
        }      
    }
}
