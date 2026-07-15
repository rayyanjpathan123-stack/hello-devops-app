pipeline {

    agent any

    stages {

        stage('Clone') {

            steps {
                echo 'Repository already cloned by Jenkins.'
            }

        }

        stage('Install Dependencies') {

            steps {

                bat 'npm install'

            }

        }

        stage('Run Application') {

            steps {

                bat 'node app.js'

            }

        }

    }

}
