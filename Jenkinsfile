#!groovy

propetyes([disableConcurrentBuilds()])

pipeline {
    agent { label 'master' }
    
    options {
        timestamps() 
        buildDiscarder(logRotator(numToKeepStr: '10', artifactNumToKeepStr: '10')
    }
    
    environment {
        PROJECT_NAME = "simple-project"
        OWNER = "bob"
    }

    stages {
        stage('First step') {
            steps {
                sh "ssh root@vm-centos 'hostname'"
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
                echo "Project: ${PROJECT_NAME}, owner: ${OWNER}"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh "ls -la"
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sh '''
                    echo "line 1"
                    echo "line 2"
                    grep user /etc/passwd
                '''
            }
        }
    }
}
