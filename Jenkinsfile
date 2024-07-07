pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                git branch: 'main', changelog: false, credentialsId: 'rakib', poll: false, url: 'git@github.com:rakib4kbd/wp-deployment.git'
            }
        }
        stage('Test') {
            steps {
                ansiblePlaybook credentialsId: 'rakib', inventory: 'inventory', playbook: 'deployWordpress.yml'
            }
        }
    }
}