node {
    stage('Agent Docker Intialization'){
        docker.image('python:3.6').inside('-p 3000:3000'){
            echo "Image successfully initialized!"
            stage("Checkout"){
                checkout scm
            }
            stage('Build'){
                virtualenv .venv
                source .venv/bin/activate
                sh 'pip install --no-cache-dir -r requirements.pip'
                sh 'pip install --no-cache-dir -r dev-requirements.pip'
            }
            // stage("Test"){
            //     sh "./jenkins/scripts/test.sh"
            // }
        }
    }
}