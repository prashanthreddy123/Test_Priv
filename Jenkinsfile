pipeline {
    agent any
    tools {
        maven "Default"
        jdk 'Default'
    }
    stages {
        stage('record test') {
            steps {
                git 'https://github.com/prashanthreddy123/Test_Priv.git'
                bat "mvn clean test"
                junit 'target/surefire-reports/*.xml'
            }
        }
    }
}
