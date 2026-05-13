#!/usr/bin/env groovy

pipeline {
    agent any
    stages {
        stage("test") {
            steps {
                script {
                    echo "Testing the application..."
                }
            }
        }
        stage("build") {
            steps {
                script {
                    echo "Building the application..."
                }
            }
        }
        stage("deploy") {
            steps {
                script {
                    def dockerCmd = 'docker run -p 3080:3080 -d aravintharaj04/maven-repo:jma-4.0'
                    sshagent(['ec2-user']) {
                        sh "ssh -o StrictHostKeyChecking=no ec2-user@40.192.100.141 ${dockerCmd}"
                    }
                }
            }
        }
    }
}
