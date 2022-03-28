pipeline{
    agent {
        docker {
                image 'maven:3.8.4-jdk-11-slim'
                args '-v /Users/santinoyanz/.m2:/root/.m2'
            }
    }
    stages {
        stage('Build') {
            steps {
                    sh 'mvn clean -U package'
                }
            }
        stage('test') {
            steps {
                    sh 'mvn test'
                }
            post {
                    always {
                            junit 'target/surefire-reports/*.xml'
                        }
                }
            }
    }
}
