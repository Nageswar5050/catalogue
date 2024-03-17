pipeline {
    agent {
        node {
            label 'agent_1'
        }
    }

    options {
        timeout(time: 1, unit: 'HOURS')
        disableConcurrentBuilds()
        ansiColor('xterm')
    }

    environment {
        packageVersion = ""
    }

    stages {
        stage ('GetVersion') {
            steps {
                script {
                    packageJson = readJSON file: 'package.json'
                    packageVersion = packageJson.version
                    echo "${packageVersion}"
                }
            }
        }

        stage ('Building') {
            steps {
                sh """
                    dnf module disable nodejs -y
                    dnf module enable nodejs:18 -y
                    dnf install nodejs -y
                    npm install
                """
        }
    }
}