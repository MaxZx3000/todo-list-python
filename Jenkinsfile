node {
    stage('Agent Docker Intialization'){
        docker.image('python:3.6').inside('-p 3000:3000'){
            echo "Image successfully initialized!"
            stage('Build'){
                sh 'pip install --target ${env.WORKSPACE} -r requirements.pip'
                sh 'pip install --target ${env.WORKSPACE} -r dev-requirements.pip'
            }
            // stage("Test"){
            //     sh "./jenkins/scripts/test.sh"
            // }
        }
    }
}