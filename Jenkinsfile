pipeline {
    agent {
        docker {
            image 'jenkins-node:latest'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'printenv'
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn -B clean package'
            }
        }
    }
}
