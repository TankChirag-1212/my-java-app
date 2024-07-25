pipeline {
    agent any

    tools {
        maven 'Maven_3.9.0' // Ensure this matches your Maven tool name
    }

    stages {    
        stage('Build') {
            steps {
                echo 'Building the Java application...'
                sh "${env.MAVEN_HOME}/bin/mvn clean install"
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh "${env.MAVEN_HOME}/bin/mvn test"
            }
    
        }
    }
    post {
        success {
            echo 'Build and test succeeded!'
        }
        failure {
            echo 'Build or test failed!'
        }
    }
}