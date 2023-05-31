node {
    stage('Agent Docker Intialization'){
        docker.image('python:3.6').inside('-p 3000:3000'){
            echo "Image successfully initialized!"
            stage('Build'){
                sudo sh 'pip install -r requirements.pip'
                sudo sh 'pip install -r dev-requirements.pip'
            }
            stage('Test'){

            }
            // stage("Test"){
            //     sh "./jenkins/scripts/test.sh"
            // }
        }
    }
}