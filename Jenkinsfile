library identifier: 'shared-lib-demo@main', retriever: modernSCM(
[$class: 'GitSCMSource',
 remote: "{params.shared_lib}"])

pipeline {
    agent any
    
    environment{
        PATH = "/usr/local/bin:${env.PATH}"
    }
    
    stages {
        stage('dev-build') {
            steps {
                script{
                    sh "rm -r docker-practical"
                    output = checkoutrepo.checkoutRepo 'https://github.com/jitendra-github-lab/docker-practical.git'
                    echo "OUTPUT : ${output}"                    
                }
            }
        }      
    }
}
