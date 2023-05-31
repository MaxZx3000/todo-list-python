node {
    stage('Agent Docker Intialization'){
        docker.image('python:3.6-slim').inside('-p 3000:3000'){
            echo "Image successfully initialized!"
            stage('Build'){
                pip install -r requirements.pip
                pip install -r dev-requirements.pip
            }
            // stage("Test"){
            //     sh "./jenkins/scripts/test.sh"
            // }
        }
    }
}