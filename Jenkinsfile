pipeline {
    agent {
        node {
            label 'agent_1'
        }
    }

    options {
        timeout(time: 1, unit: 'HOURS')
        disableConcurrentBuils()
        ansiColour('xterm')
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
    }
}