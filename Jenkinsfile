pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh '''
                mvn clean package
                java -jar -Dspring.profiles.active=test target/spring-boot-rest-example-0.5.0.war
                '''
            }
        }
        stage('Testing Application') {
            steps {
            	echo 'running curl command'
                sh '''
                curl localhost:8090/swagger-ui.html
                '''
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}