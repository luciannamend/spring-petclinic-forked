pipeline {
    agent any

    environment {
        MAVEN_HOME = "C:/Program Files/apache-maven-3.9.9" 
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', 
                    url: 'https://github.com/luciannamend/spring-petclinic-forked.git'
            }
        }       

        stage('Code Coverage') {
            steps {
                script {
                    bat './mvnw jacoco:report'  // Runs Jacoco to generate the coverage report
                }
            }
        }       
    }

    post {
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
