pipeline {
    agent any
    tools {
        maven "Default"
        jdk 'Default'
    }
    stages {
        stage('record test') {
            steps {
                git 'https://github.com/nagarjunagr8/testsuite.git'
                bat "mvn clean test"
                junit 'target/surefire-reports/*.xml'
            }
            agent {
                label 'pr_agent'
            }
            environment {
                JAVA_HOME = "C:\Program Files\Java\jdk1.8.0_201"
            }
        }
    }
}
