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
                    yum module disable nodejs -y
                    yum module enable nodejs:18 -y
                    yum install nodejs -y

                    npm install

                    ls -la 
                """
            }
        }
    }
}