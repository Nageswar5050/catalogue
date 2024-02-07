pipeline {
    agent {
        node {
            label 'Agent_1'
    }   }

    environment {
        packageVersion = ' '
    }
    stages {
        stage ("get version from catalogue code") {
            steps {
                script {
                    def packageJson = readJSON file: 'package.json'
                    packageVersion = packageJson.version
                    echo "catalogue application version : $packageVersion"
                }
            }
        }

        stage ("install dependencies") {
            steps {
                sh """
                    npm install

                    ls -la 
                """
            }
        }
    }
}