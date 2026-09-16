pipeline {
    agent any 
    parameters {
    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
    text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
    booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
    choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
    password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    
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

