pipeline {

    agent {
        label 'vm'
    }
        
    stages {
        stage("compile") {
            steps {
                sh "mvn compile"
            }
        }

        stage("test") {

            steps{
                sh "mvn test"
                junit 'target/surefire-reports/*.xml'
            }
        }

        stage("run") {

            steps{
                sh "mvn exec:java"
            }
        }
    }

}
