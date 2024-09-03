pipeline {
    agent any
    tools { 
        nodejs "NodeJS 22.7.0"  // Make sure this matches the NodeJS version configured in Jenkins
        gradle "gradle"        // Update this to match the name in your Jenkins Global Tool Configuration
    }
    stages {
        stage('Clone Repository') {
            steps { 
                git 'https://github.com/Gerrykiptoo/docker_wokshop_react'
            }
        }
        stage('Build Project') {
            steps {
                dir('project-directory') { // Change to the subdirectory containing the Gradle build files
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
