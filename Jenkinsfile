pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Pull code from your source control
                git url: 'https://github.com/you/your-laravel-app.git', branch: 'main'
            }
        }
        stage('Composer Install') {
            steps {
                // Run Composer inside the PHP-FPM container
                sh 'docker-compose exec php-fpm composer install --no-interaction'
            }
        }
        stage('Test') {
            steps {
                // Run your tests
                sh 'docker-compose exec php-fpm php artisan test'
            }
        }
    }
}
