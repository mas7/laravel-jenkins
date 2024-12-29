pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Pull code from your source control
                git url: 'https://github.com/mas7/laravel-jenkins.git', branch: 'main'
            }
        }
        stage('Composer Install') {
            steps {
                // Run Composer inside the PHP-FPM container
                sh 'sudo docker-compose exec php-fpm composer install --no-interaction'
            }
        }
        stage('Test') {
            steps {
                // Run your tests
                sh 'sudo docker-compose exec php-fpm php artisan test'
            }
        }
    }
}
