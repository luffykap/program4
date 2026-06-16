
pipeline {
    agent any

    tools {
        jdk 'jdk'
        maven 'maven'
    }

    stages {

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }

        stage('Run') {
            steps {
                sh 'mvn exec:java -Dexec.mainClass="com.luffy.App"'
            }
        }
        stage('Verify') {
    steps {
        sh 'cat destination.txt'
    }
}
    }

    post {
        success {
            echo 'Build Successful ✅'
        }
        failure {
            echo 'Build Failed ❌'
        }
    }
}
