pipeline {
    agent {
         label 'agent-1'
    }
    options {
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
    }

    Parameters{
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

     environment{
        DEPLOY_TO =  'production'
        GREETING = 'Good Morning'
        // GIT_CREDENTIALS_ID = 'githubuser1'
        // GIT_URL = "https://github.com/SatraHIS/his-staff-ts-next.git"
    }


    stages {
        stage('build') {
            steps {
                 sh 'echo This is build'
                sh 'env'
            }
        }

        stage('Test') {
            steps {
                sh 'echo This is Test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo This is Deploy'
            }
        }

        stage ('print_params') {
            steps {
                echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "Toggle: ${params.TOGGLE}"
                echo "Choice: ${params.CHOICE}"
                echo "Password: ${params.PASSWORD}"
                echo "triggered test again"
                error 'some failure'
            }
        }
    }

    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        success { 
            echo 'I will run when pipeline is success'
        }
        failure { 
            echo 'I will run when pipeline is failure'
        }
    }
}