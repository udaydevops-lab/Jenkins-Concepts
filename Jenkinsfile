pipeline {
    agent {
         label 'agent-1'
    }
    stages {
        stage('Example') {
            steps {
                echo 'Hello World'
            }
        }

        stage('testwebhook') {
            steps {
                echo 'Hello this is from stage 2'
            }
        }
        stage('testagent') {
            steps {
                echo 'Hello this is for testing the agent configuration'
            }
        }
    }
}