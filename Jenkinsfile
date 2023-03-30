node {
    docker.image('node:16-buster-slim').inside('-p 3000:3000') {
        stage('Build') {

                sh 'npm install'

            }

        stage('Test') { 

                sh './jenkins/scripts/test.sh' 
        }

        stage('Deploy') { 
                sh './jenkins/scripts/deliver.sh'
                input message: 'Lanjutkan ke tahap Deploy?(Klik "Proceed" untuk mengakhiri)'
                sleep 60 
                sh './jenkins/scripts/kill.sh' 
        }

    }

}
