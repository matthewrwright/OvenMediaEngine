node('jenkinsbuildserver') {
stage('Checkout'){
    checkout scm
}

stage('Build and Push'){

    docker.withRegistry('https://sprout.phdata.co.uk', 'docker') {

        def customImage = docker.build("ovenmediaengine:${env.BUILD_ID}")

        /* Push the container to sprout */
        customImage.push()
        customImage.push("${env.BRANCH_NAME}")
    }
	}
}