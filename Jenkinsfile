node {
    checkout scm

    docker.withRegistry('https://sprout.phdata.co.uk', 'docker') {

        def customImage = docker.build("ovenmediaengine:${env.BUILD_ID}")

        /* Push the container to the custom Registry */
        customImage.push()
        customImage.push('latest')
    }
}