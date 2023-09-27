pipeline {
    agent any
    
    tools{
        jdk 'jdk17'
        maven 'maven3'
    }

    stages {
        stage('Git Checkout') {
            steps {
                git branch: 'feature1', url: 'https://github.com/dbhandari07/demo-spring-petclinic.git'
            }
        }
        
        stage('Compile') {
            steps {
                sh "mvn clean compile"
            }
        }
        
        stage('Package') {
            steps {
                sh "mvn clean package -DskipTests=true"
            }
        }
        
        stage('Deploy') {
            steps {
                sh "cp target/petclinic.war /usr/local/apache/apache-tomcat-9.0.50/webapps"
            }
        }
    }
}
