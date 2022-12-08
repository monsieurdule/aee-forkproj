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
                jiraComment body: 'komentar', issueKey: 'JIR-1'
            }
        }
    }

    post {
        success {
            #httpRequest customHeaders: [[maskValue: false, name: 'build', value: 'success']], httpMode: 'POST', requestBody: '"build" : "success"', responseHandle: 'NONE', url: 'http://192.168.10.200:5000/jenkinshook', wrapAsMultipart: false
            httpRequest acceptType: 'APPLICATION_JSON', contentType: 'APPLICATION_JSON', httpMode: 'POST', requestBody: '"build" : "success"', responseHandle: 'NONE', url: 'http://192.168.10.200:5000/jenkinshook', wrapAsMultipart: false
        }
    }

}
