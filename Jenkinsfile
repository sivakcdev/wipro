pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'scp -r /var/lib/jenkins/workspace/m2/target/*.jar  root@two:/root/apache-tomcat-8.5.43/webapps'
            }
        }
    }
}
