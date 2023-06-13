node {
    withDockerContainer(args: '-p 3000:3000', image: 'node:lts-buster-slim') {
        //stage('pull') { 
        //    checkout([$class: 'GitSCM', branches: [[name: '*/react-app']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/zhatotech/a428-cicd-labs.git']]])
        //}
        stage('Build') { 
            sh 'npm install'
        }
        stage('Test') {
            sh './jenkins/scripts/test.sh'
        }
    }
}
