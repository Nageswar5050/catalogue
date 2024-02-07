pipeline {
    agent any

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
                    sudo apt-get update -y
                    sudo apt-get install nodejs -y

                    ls -la 
                """
            }
        }
    }
}