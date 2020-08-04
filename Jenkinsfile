pipeline {
    agent any

    stages {
        stage('Pre Cleanup Workspace') {
            steps {
                script {
                    sh label: '', script: 'docker system prune -f > /dev/null 2>&1'
                    cleanWs()
                }
            }
        }
        stage('Checkout SCM') {
            steps {
                script {
                   git credentialsId: 'githubcredentials', url: 'https://github.com/sheetalrajan99/Assessment.git'
                }
            }
        }
        stage('NPM Install') {
            steps {
                script {
                   sh label: '', script: 'npm install'
                }
            }
        }
        stage('Post Cleanup Workspace') {
            steps {
                script {
                    sh label: '', script: 'docker system prune -f > /dev/null 2>&1'
                    cleanWs()
                }
            }
        }
    }
}