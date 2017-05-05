node {
    stage "Prepare environment"
        checkout scm
        def environment  = docker.build 'dev-node'

        environment.inside {
            stage "Checkout and build deps"
                sh "npm install"
                sh "pm2 start app.js"

            stage "Test and validate"
                sh "mocha"
                junit 'reports/**/*.xml'
        }

    stage "Cleanup"
        deleteDir()
}