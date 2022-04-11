pipeline {
     agent any
     tools {nodejs "17.9.0"}
     stages {
        stage("Build") {
            steps {
                sh 'npm install'
                sh "npm run build"
            }
        }
    }
}