pipeline {
    agent any
    stages {
        stage('record test') {
            steps {
                git branch='dev',  'https://github.com/nagarjunagr8/testsuite.git'
                bat "mvn clean test"
                junit 'target/surefire-reports/*.xml'
            }
            agent {
                label 'pr_agent'
            }
            tools {
                maven "pr_mvn"
                jdk 'pr_jdk'
            }
        }
    }
}
