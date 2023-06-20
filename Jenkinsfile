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
            input message: 'Lanjutkan ketahap Deploy? (Klik "Proceed" untuk mengakhiri)' 
        }
        stage('Deploy') { 
            sh './jenkins/scripts/deliver.sh' 
            sleep 60
            sh './jenkins/scripts/kill.sh' 
        }
    }
}
