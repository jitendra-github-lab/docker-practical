library identifier: 'shared-lib-demo@main', retriever: modernSCM(
[$class: 'GitSCMSource',
 remote: "https://github.com/jitendra-github-lab/shared-lib.git"])

pipeline {
    agent any
    
    environment{
        PATH = "/usr/local/bin:${env.PATH}"
    }
    
    stages {
        stage('dev-build') {
            steps {
                script{
                    withCredentials([string(credentialsId: 'my-shared_lib', variable: 'SECRET')]) { //set SECRET with the credential content
                        echo "My secret text is '${SECRET}'"
                    }
                    sh "rm -r docker-practical"
                    output = checkoutrepo.checkoutRepo 'https://github.com/jitendra-github-lab/docker-practical.git'
                    echo "OUTPUT : ${output}"                    
                }
            }
        }      
    }
}
