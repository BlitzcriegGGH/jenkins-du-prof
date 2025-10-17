pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[
                        credentialsId: 'MACLEOHSECOURS',
                        url: 'https://github.com/BlitzcriegGGH/jenkins-du-prof.git'
                    ]]
                ])
                echo 'Cloning repository...'
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