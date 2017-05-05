node {
    stage "Prepare environment"
        checkout scm
        def environment  = docker.build 'dev-node'

        environment.inside {
            stage "Checkout and build deps"
                sh "npm install"
                sh "nmp install gulp"

            stage "Test and validate"
                sh "npm install gulp-cli && ./node_modules/.bin/gulp"
                junit 'reports/**/*.xml'
        }

    stage "Cleanup"
        deleteDir()
}