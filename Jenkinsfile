node {
    stage("Prepare environment") {
       
        checkout scm
       
        docker.image('node:6.10.3').inside {
           stage "Checkout and build deps"
                sh "su -"
                sh "npm install"

            stage "Test and validate"
                sh "mocha"
        }
    }
    stage "Cleanup"
        deleteDir()
}
