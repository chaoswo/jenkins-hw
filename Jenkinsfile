pipeline {
    agent any

    stages {
        stage('install-pip-deps') {
            steps {
                echo '... installing pip dependancies...'
                git branch: 'main', url: 'https://github.com/chaoswo/python-greetings'
                bat 'dir'
                bat 'pip install -r requirements.txt'
            }
        }
        stage('deploy-to-dev') {
            steps {
                echo '... deploying to development...'
                git branch: 'main', url: 'https://github.com/chaoswo/python-greetings'
                bat 'dir'
                bat "C:\\Users\\Gita\\AppData\\Roaming\\npm delete greetings-app-dev  & EXIT /B 0"
                bat 'pm2 start app.py --name greetings-app-staging -- --port 7002'
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
                git branch: 'main', url: 'https://github.com/mtararujs/python-greetings'
                bat 'pm2 delete greetings-app-staging  & EXIT /B 0'
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
                git branch: 'main', url: 'https://github.com/mtararujs/python-greetings'
                bat 'pm2 delete greetings-app-preprod  & EXIT /B 0'
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
                git branch: 'main', url: 'https://github.com/mtararujs/python-greetings'
                bat 'pm2 delete greetings-app-prod  & EXIT /B 0'
            }
        }
        stage('tests-on-prod') {
            steps {
                echo '...testing on production...'
            }
        }
    }
} 