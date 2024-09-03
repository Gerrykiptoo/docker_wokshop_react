pipeline {
    agent any
    tools { 
        nodejs "NodeJS 22.7.0"
        gradle "gradle"
    }
    stages {
        stage('Clone Repository') {
            steps { 
                git branch: 'main', url: 'https://github.com/Gerrykiptoo/docker_wokshop_react'
            }
        }
        stage('Build Project') {
            steps {
                dir('project-directory') {
                    sh 'gradle build'
                }
            }
        }
        stage('Run Tests') {
            steps {
                dir('project-directory') {
                    sh 'npm install mocha'
                    sh 'npm test'
                    sh 'gradle test'
                }
            }
        }
    }
}
