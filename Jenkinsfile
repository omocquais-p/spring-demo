pipeline {
    agent {
        docker {
            image 'jenkins-node:latest'
            args '-v ${env.WORKSPACE}/maven-repo:/root/.m2'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'printenv'
                sh 'echo ${env.WORKSPACE}'
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
