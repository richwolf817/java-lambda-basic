pipeline {
agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deliver') {
            steps {
                sh 'aws lambda update-function-code --function-name ZipTest --zip-file fileb:///var/lib/jenkins/workspace/simple-java-maven-app/target/my-app-1.0-SNAPSHOT.jar'
            }
        }
    }
}
