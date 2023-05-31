node {
    docker.image('mongo:5.0.15').withRun('-h localhost -p 27017:27017'){ c ->
        docker.image('python:3.6').inside("-p 3000:3000 --link ${c.id}:db"){
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
                    sh 'python -m pytest'
                }
            }
        }
    }
}