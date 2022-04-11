def remote = [:]
    remote.name = 'test'
    remote.host = 'test.domain.com'
    remote.user = 'ec2-ser'
    remote.password = 'password'
    remote.allowAnyHosts = true
pipeline {
     agent any
     tools {nodejs "node"}
     stages {
        stage("Build") {
            steps {
                sh "npm install"
                sh "npm run build"
            }
        }
    }
}