pipeline {
    agent any
    environment {
        username = 'Gaurav Sharma'
    }
    parameters {
        string(name: 'person', defaultValue: 'Abhishek Sharma', description: "How are you")
        booleanParam(name: 'isMale', defaultValue: 'true', description: "")
        choice(name: 'City', choices: ['Mumbai','Rajasthan','Delhi'], description: "")
    }
    stages {
        stage('Run a Command') {
            steps {
                sh '''
                ls
                pwd
                date
                whoami
                '''
            }
        }
        stage('Environment Variable') {
            environment{
                name = 'Chirag Sharma'
            }
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'
                sh 'echo "${username}"'
            }
        }
        stage('Parameters') {
            steps {
                echo 'deploy to test'
                sh 'echo "${name}"'
                sh 'echo "${username}"'
                sh 'echo "${person}"'
                sh 'echo "${isMale}"'
                sh 'echo "${City}"'
            }
        }
        stage('continue ?') {
            input {
                message "SHould we continue ?"
                ok "Yes, we should"
            }
            steps {
                echo 'deploy to prod'
            }
        }
        stage('deploy to prod') {
            steps {
                echo 'deploy to prod'
            }
        }
    }
        post {
            always {
                echo "Hi! This is my first website"
            }
            success {
                echo "Hey! Here I get success"
            }
            failure {
                echo "I got failure"
            }
        }
}
