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
        stage('Deploy') { 
            sh './jenkins/scripts/deliver.sh' 
            // input message: 'Sudah selesai menggunakan React App? (Klik "Proceed" untuk mengakhiri)' 
            sh './jenkins/scripts/kill.sh' 
        }
    }
}
