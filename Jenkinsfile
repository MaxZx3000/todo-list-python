node {
    stage('Agent Docker Intialization'){
        docker.image('python:3.6').inside('-p 3000:3000'){
            echo "Image successfully initialized!"
            stage('Build'){
                sh 'pip install -r requirements.pip'
                sh 'pip install -r dev-requirements.pip'
            }
            stage('Test'){

            }
            // stage("Test"){
            //     sh "./jenkins/scripts/test.sh"
            // }
        }
    }
}