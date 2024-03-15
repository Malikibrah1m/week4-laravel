node {
    checkout scm
    // deploy env dev
    stage("Build") {
        docker.image('myjenkins-blueocean:2.440.1-1').inside('-u root') {
            sh 'rm composer.lock'
            sh 'composer install'
        }
    }
    // Testing
    docker.image('myjenkins-blueocean:2.440.1-1').inside('-u root') {
        sh 'echo "Ini adalah test"'
    }
}
