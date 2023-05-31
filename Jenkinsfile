node {
    stage('Agent Docker Intialization'){
        docker.image('python:3.6').inside('-p 3000:3000'){
            echo "Image successfully initialized!"
            stage("Checkout"){
                checkout scm
            }
            stage('Build'){
                withEnv(["HOME=${env.WORKSPACE}"]) {
                    sh 'python -m pip install --user -r requirements.pip'
                    sh 'python -m pip install --user -r dev-requirements.pip'
                }
            }
            stage('Test'){
                docker.image('mongodb:latest').inside('-p 5000:5000'){
                    // sh 'sudo service mongodb start'
                    withEnv(["HOME=${env.WORKSPACE}"]){
                        sh 'python -m pytest'
                    }
                }
            }
        }
    }
}