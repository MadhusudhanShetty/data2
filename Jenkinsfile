pipeline {
    agent any 
    parameters {
    string(name: 'PERSON', defaultValue: 'Jenkins', description: 'Who should I say hello to?')
    text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
    booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
    choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
    password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    environment {
        BRANCH  = 'main'
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
                catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') {
            sh '''
                sleep 10
                exit 1
            '''
            }
        }
        stage('Deploy') { 
            steps {
                   script {
                    try {
                        // Code that might throw an exception
                        sh 'some-command-that-might-fail'
                    } catch (Exception e) {
                        // Handling the exception
                        echo "Caught an exception: ${e.message}"
                        // Mark the build as failed
                        currentBuild.result = 'FAILURE'
                    } finally {
                        // Runs regardless of exception
                        echo "Cleaning up resources..."
                    }
            }
        }
    }
}

