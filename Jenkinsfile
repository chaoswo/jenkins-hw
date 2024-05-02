pipeline {
    agent any

    stages {
        stage('install-pip-deps') {
            steps {
                echo '... installing pip dependancies...'
                git branch: 'main', url: 'https://github.com/mtararujs/python-greetings'
                sh 'ls -la'
                sh 'pip3 install -r requirements.txt'
            }
        }
        stage('deploy-to-dev') {
            steps {
                echo '... deploying to development...'
            }
        }
        stage('tests-on-dev') {
            steps {
                echo '... testing on development...'
            }
        }
        stage('deploy-to-staging') {
            steps {
                echo '... deploying to staging...'
            }
        }
        stage('tests-on-staging') {
            steps {
                echo '... testing on staging...'
            }
        }
        stage('deploy-to-preprod') {
            steps {
                echo '... deploy to pre-production...'
            }
        }
        stage('tests-on-preprod') {
            steps {
                echo '... testing on pre-production...'
            }
        }
        stage('deploy-to-prod') {
            steps {
                echo '... deploying to production...'
            }
        }
        stage('tests-on-prod') {
            steps {
                echo '...testing on production...'
            }
        }
    }
} 