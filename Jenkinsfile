node {
    checkout scm

    // deploy env dev
    stage("Build"){
        docker.image('php:7.4-apache').inside('-u root') {
            sh 'rm composer.lock'
            sh 'composer install'
        }
    }
}


    // Testing
    stage("Test"){
        docker.image('php:7.4-cli').inside('-u root') {
            sh 'php artisan test --testsuite=Unit'
        }
    }
