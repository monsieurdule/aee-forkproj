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
            }
        }

        stage("run") {

            steps{
                sh "mvn exec:java"
            }
        }

    }
    post {
            always {
                junit(testResults: 'reports/*.xml', allowEmptyResults : true)
            }
        }
}
