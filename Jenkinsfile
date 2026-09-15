pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                sh '''
                    echo "Building stage..."
                    # Add your build commands here
                    ls -lrth
                ''' 
            }
        }
        stage('Test') { 
            steps {
                sh '''
                    echo "testing stage"
                    # Add your test commands here
                    #bin/bash 
                    sleep 2 
                '''
            }
        }
        stage('Deploy') { 
            steps {
                sh '''
                    echo "Deploying stage..."
                    # Add your deploy commands here
                '''
            }
        }
    }
}

