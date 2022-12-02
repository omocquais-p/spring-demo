pipeline {
    agent {
        docker {
            image 'jenkins-node:latest'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'ls -l'
                sh 'touch build.step'
                sh 'ls -l'
                sh 'printenv'
                sh 'ls -l /root/.m2'
                sh 'mvn -B -DskipTests clean package'
                sh 'ls -l /root/.m2'
            }
        }
        stage('Test') {
            steps {
                sh 'touch test.step'
                sh 'ls -l'
                sh 'mvn -B clean package'
                sh 'ls -l /root/.m2'

            }
        }
    }
}
