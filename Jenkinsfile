node {
    stage('Agent Docker Intialization'){
        docker.image('mongo:7.0').inside('-p 3000:3000'){
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
                withEnv(["HOME=${env.WORKSPACE}"]){
                    // sh 'sudo service mongodb start'
                    sh 'python -m pytest'
                }
            }
        }
    }
}