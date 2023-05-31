node {
    stage('Agent Docker Intialization'){
        docker.image('python:3.6').inside('-p 3000:3000'){
            echo "Image successfully initialized!"
            stage("Checkout"){
                checkout scm
            }
            stage('Build'){
                sh 'pip install --no-cache-dir --user -r requirements.pip'
                sh 'pip install --no-cache-dir --user -r dev-requirements.pip'
            }
            // stage("Test"){
            //     sh "./jenkins/scripts/test.sh"
            // }
        }
    }
}