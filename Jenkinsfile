pipeline {
    agent any
    tools {
        nodejs "NodeJS 22.7.0"
    }
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Gerrykiptoo/docker_wokshop_react'
            }
        }
        stage('Install Dependencies') {
            steps {
                dir('project-directory') {
                    sh 'npm install'
                }
            }
        }
        stage('Build Project') {
            steps {
                dir('project-directory') {
                    sh 'npm run build'
                }
            }
        }
        stage('Run Tests') {
            steps {
                dir('project-directory') {
                    sh 'npm test'
                }
            }
        }
    }
}
