pipeline {
    agent any
    environment {
        name =  "aditya"
    }
    parameters{
        string(name: 'person', defaultValue: 'Aditya Verma', description: "Who are you?")
        booleanParam(name: 'isMale', defaultValue: true, description: "")
        choice(name: 'City', choices: ['Delhi', 'Banaglore'], description: "")
    }

    stages {
        stage('Run a command') {
            steps {
                sh '''
                ls
                date
                pwd
                cal
                '''
            }
        }
        stage('Environment Variables') {
            environment {
                username =  "adityaverma"
            }
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'
                sh 'echo "${username}"'
            }
        }
        stage('Parameters') {
            steps {
                echo 'Parameters'
                sh 'echo "${person}"'
            }
        }
        stage('Continue?') {
            input{
                message "Should we continue?"
                ok "Yes, we should!"
            }
            steps {
                echo 'Deploy on prod'
            }
        }
        stage('Deploy on prod') {
            steps {
                echo 'Deploy on prod'
            }
        }
    }
    post{
        always{
            echo 'I will always run'
        }
    }
}
