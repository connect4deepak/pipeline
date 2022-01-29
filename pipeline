pipeline {
    agent any
    environment {
        myname = 'Deepak'
    }
    parameters {
        string(name: 'person', defaultValue: 'dodo', description: "who are you?")
    }     
    stages {
        stage('Test') {
            environment {
            username = 'Daksh'
        }   
            steps {
                sh '''
                echo 'Test'
                pwd
                date
                ls
                '''
            }
        }
        stage('Build & Environment Variables') {
            environment {
                username = 'Rahul'
            }   
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${myname}"'
                sh 'echo "${username}"'
                sh 'echo "${person}"'
            }
        }
        stage('This is Test') {
            steps {
                echo 'This is Test'
            }
        }
        stage('Continue ?') {
            input {
                message 'Should we continue?'
                ok 'Yes we should!'
            }
            steps {
                echo 'Deploy on Prod'
            }
        }
        stage('This is Prod') {
            steps {
                echo 'This is Prod'
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure { 
            echo 'failure'
        }
        success { 
            echo 'success'
        }
    }    
}    
