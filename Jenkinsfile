pipeline {
    agent {
        label "nodejs"
    }
    stages {
        stage("Install dependencies") {
            steps {
                sh "npm ci"
            }
        }
        stage("Check Style") {
            steps {
                echo "Hello from Jenkins Pipeline!"
            }
        }
        stage("Test") {
            steps {
                sh "npm test"
            }
        }
        stage('Release') {
            steps {
                sh '''
oc project cmfrmz-greetings
oc start-build greeting-console --follow --wait
'''
            }
        }
    }
}
