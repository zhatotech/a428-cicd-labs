node {
    checkout scm
    docker.image('node:16-buster-slim').withRun('-p 3000:3000')  {
        sh 'npm install'
    }
}


// node {
//     docker {
//         image 'node:16-buster-slim' 
//         args '-p 3000:3000' 
//     }
//     stage('Build') { 
//         sh 'npm install' 
//     }
//     // stage('Test') {
//     //     steps {
//     //         sh './jenkins/scripts/test.sh'
//     //     }
//     // }
// }
