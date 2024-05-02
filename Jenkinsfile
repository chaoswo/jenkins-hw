pipeline {
    agent any

    stages {
        stage('install-pip-deps') {
            steps {
                echo '... installing pip dependancies...'
                git branch: 'main', url: 'https://github.com/chaoswo/python-greetings'
                bat "npm install pm2 -g"
                bat "dir"
                bat "pip3 install -r requirements.txt"
            }
        }
        stage('deploy-to-dev') {
            steps {
                echo '... deploying to development...'
                git branch: 'main', url: 'https://github.com/chaoswo/python-greetings'
                bat 'npm install'
                bat "C:\\Users\\Gita\\AppData\\Roaming\\npm\\node_modules\\pm2 delete \"greetings-app-dev\"  & EXIT /B 0"
                bat "C:\\Users\\Gita\\AppData\\Roaming\\npm\\node_modules\\pm2 start app.py --name \"greetings-app-dev\" -- --port= 7001"
            }
        }
        stage('tests-on-dev') {
            steps {
                echo '... testing on development...'
                git branch: 'main', url: 'https://github.com/chaoswo/course-js-api-framework'
                bat "npm install"
                bat "npm run greetings greetings_dev"
                bat "C:\\Users\\Gita\\AppData\\Roaming\\npm\\node_modules\\pm2 delete \"greetings-app-dev\" & EXIT /B 0"
            }
        }
        stage('deploy-to-staging') {
            steps {
                echo '... deploying to staging...'
                git branch: 'main', url: 'https://github.com/chaoswo/python-greetings'
                bat 'dir'
                bat "C:\\Users\\Gita\\AppData\\Roaming\\npm\\node_modules\\pm2 delete greetings-app-staging  & EXIT /B 0"
                bat "C:\\Users\\Gita\\AppData\\Roaming\\npm\\node_modules\\pm2 start app.py --name greetings-app-staging -- --port= 7002"
            }
        }
        stage('tests-on-staging') {
            steps {
                echo '... testing on staging...'
                git branch: 'main', url: 'https://github.com/chaoswo/course-js-api-framework'
                bat "npm install"
                bat "npm run greetings greetings_staging"
                bat "C:\\Users\\Gita\\AppData\\Roaming\\npm\\node_modules\\pm2 delete \"greetings-app-staging\" & EXIT /B 0"
            
            }
        }
        stage('deploy-to-preprod') {
            steps {
                echo '... deploy to pre-production...'
                git branch: 'main', url: 'https://github.com/chaoswo/python-greetings'
                bat 'dir'
                bat "C:\\Users\\Gita\\AppData\\Roaming\\npm\\node_modules\\pm2 delete greetings-app-preprod  & EXIT /B 0"
                bat "C:\\Users\\Gita\\AppData\\Roaming\\npm\\node_modules\\pm2 start app.py --name greetings-app-preprod -- --port= 7003"
            }
        }
        stage('tests-on-preprod') {
            steps {
                 echo '... deploy to pre-production...'
               git branch: 'main', url: 'https://github.com/chaoswo/course-js-api-framework'
                bat "npm install"
                bat "npm run greetings greetings_preprod"
                bat "C:\\Users\\Gita\\AppData\\Roaming\\npm\\node_modules\\pm2 delete \"greetings-app-preprod\" & EXIT /B 0"
            }
        }
        stage('deploy-to-prod') {
            steps {
                echo '... deploying to production...'
               git branch: 'main', url: 'https://github.com/chaoswo/python-greetings'
                bat 'dir'
                bat "C:\\Users\\Gita\\AppData\\Roaming\\npm\\node_modules\\pm2 delete greetings-app-prod  & EXIT /B 0"
                bat "C:\\Users\\Gita\\AppData\\Roaming\\npm\\node_modules\\pm2 start app.py --name greetings-app-prod -- --port= 7004"
            }
        }
        stage('tests-on-prod') {
            steps {
                echo '...testing on production...'
                git branch: 'main', url: 'https://github.com/chaoswo/course-js-api-framework'
                bat "npm install"
                bat "npm run greetings greetings_prod"
                bat "C:\\Users\\Gita\\AppData\\Roaming\\npm\\node_modules\\pm2 delete \"greetings-app-prod\" & EXIT /B 0"
            
            }
        }
    }
} 