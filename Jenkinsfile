pipeline {
    agent any
    environment {
        CREDENTIALS_ID = 'MACLEOHSECOURS'
        URL_GIT = 'https://github.com/BlitzcriegGGH/jenkins-du-prof.git'
    }

    stages {
        stage('Clone repository') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[
                        credentialsId: "${CREDENTIALS_ID}",
                        url: "${URL_GIT}"
                    ]]
                ])
                echo 'Cloning repository...'
                sh "printenv"
            }
        }

        stage('Readfile and print its content') {
            steps {
                echo 'Reading file... and Ready to print its content'
                script {
                    def content = readFile 'servers.csv'
                    def lines = content.split(/\r?\n/)
                    lines.each { line ->
                        echo line
                    }
                }
            }
        }

        stage('Build') {
            steps {
                echo 'Building...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'cat servers.csv'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}