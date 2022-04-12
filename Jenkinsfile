def remote = [:]
            remote.name = 'test'
            remote.host = '35.156.239.114'
            remote.allowAnyHosts = true
pipeline{
    agent any
    tools {nodejs "17.9.0"}
    
    stages{
        stage("Build"){
             steps {
                sh 'npm install'
                sh "npm run build"
            }          
        }
        
        stage("Connect and Deploy") {             
                steps {
                    withCredentials(bindings: [sshUserPrivateKey(credentialsId: 'test-server-access', keyFileVariable: 'identity', passphraseVariable: '', usernameVariable: 'user')]) {
                    script{
                        remote.user = user
                        remote.identityFile = identity
                    }
                    sh 'mv build react'
                    sshPut remote: remote, from: 'react/', into: '/usr/share/nginx'
                    }
                } 
        }
    }
}