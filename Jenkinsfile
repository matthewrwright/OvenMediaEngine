node('jenkinsbuildserver') {
    stage("Checkout"){
	checkout scm
}
stage("Build"){
    docker.withRegistry('https://sprout.phdata.co.uk', 'docker') {

        def customImage = docker.build("ovenmediaengine:${env.BUILD_ID}")
}
stage("Push"){}
        /* Push the container to sprout */
        customImage.push()
        customImage.push('latest')
		}}
    }
}