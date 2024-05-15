pipeline {
    agent any
    tools {
        nodejs 'NodeJS'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Starting Build Stage'
                // Install project dependencies
                bat 'npm install'
                // Build the Angular project
                bat 'ng build --prod'
                echo 'Build Stage Completed'
            }
        }


        stage('Deploy') {
            steps {
                echo 'Starting Deploy Stage'
                // Copy the WAR file to Tomcat webapps directory
                bat 'copy /y dist\\ROOT.war "C:\\path\\to\\tomcat\\webapps\\ROOT.war"'
                echo 'Deploy Stage Completed'
            }
        }
    }

    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
