node {
    stage("Prepare environment") {
       
        checkout scm
       
        docker.image('node:6.10.3').inside {
	   stage "Chown dir"
	       sh "chown -R $USER /usr/local"

            stage "Checkout and build deps"
                sh "npm install"

            stage "Test and validate"
                sh "mocha"
        }
    }
    stage "Cleanup"
        deleteDir()
}
