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
             withCredentials([sshUserPrivateKey(credentialsId: '81bee60d-7a5a-400a-9068-237595e0f8e7', keyFileVariable: 'identity', passphraseVariable: '', usernameVariable: 'user')]) {
        remote.user = user
        remote.identityFile = identity
                steps {
                    sshCommand remote: remote, command: "for i in {1..5}; do echo -n \"Loop \$i \"; date ; sleep 1; done"
                } 
             }
            }
    }
}