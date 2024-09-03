pipeline {
    agent any
    tools {
        nodejs "NodeJS 22.7.0" // Make sure this matches the Node.js installation in Jenkins
    }
    stages {
        stage('Clone Repository') {
            steps {
                // Clone the Git repository
                git branch: 'main', url: 'https://github.com/Gerrykiptoo/docker_wokshop_react'
            }
        }
        stage('Install Dependencies') {
            steps {
                // Install project dependencies using npm
                dir('project-directory') { // Update this path if necessary
                    sh 'npm install'
                }
            }
        }
        stage('Build Project') {
            steps {
                // Build the project using npm (or other build command specified in package.json)
                dir('project-directory') { // Update this path if necessary
                    sh 'npm run build'
                }
            }
        }
        stage('Run Tests') {
            steps {
                // Run tests using npm
                dir('project-directory') { // Update this path if necessary
                    sh 'npm test'
                }
            }
        }
    }
}
