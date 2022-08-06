pipeline {
    agent any
    environment {
        name = 'sarangi'
    }
    parameters {
        string(name: 'person',defaultValue: 'papulipu',description: 'Who are you?')
        booleanParam (
            name: 'isMale',
            defaultValue: true,
            description: ""
            )
        choice(name: 'City',choices: ['Mumbai','Delhi','Odisha'],description: '')    
    }

    stages {
        stage('Run & command') {
            steps {
                sh '''
                ls
                pwd
                date
                cal 1999
                '''
            }
        }
         stage('Environment variable') {
         environment {
             username = 'kumarpk@'
         }
            steps {
                echo 'hello piyush'
                sh "echo '${BUILD_ID}'"
                sh "echo '${name}'"
                sh "echo '${username}'"
            }
        }
         stage('Parameter') {
            steps {
                echo 'Hello World'
                sh "echo '${name}'"
                sh "echo '${person}'"
            }
        }
         stage('Continue') {
         input {
             message "should we continue"
             ok "yes we should"
         }
         steps {
                echo 'Hello World'
            }
        }
        stage('Deploy on prod') {
            steps {
                echo 'Hello World'
            }
        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}
