pipeline {
    agent any
    
    environment {
        PROJECT_NAME = "simple-project"
        OWNER = "bob"
    }

    stages {
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
