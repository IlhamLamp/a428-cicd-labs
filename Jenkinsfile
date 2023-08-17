// scripted pipeline
node {
    withDockerContainer(args: '-p 3000:3000', image: 'node:16-buster-slim') {
        stage('Build') {
            checkout scm
            sh 'npm config rm proxy'
            sh 'npm config rm https-proxy --tried removing npm proxy'
            sh 'npm install'
        }
        stage('Test') {
            sh './jenkins/scripts/test.sh'
        }
    }
}