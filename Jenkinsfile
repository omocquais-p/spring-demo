pipeline {
    agent {
        docker {
            image 'jenkins-node:latest'
            reuseNode true
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'ls -l'
                sh 'touch build.step'
                sh 'ls -l'
                sh 'printenv'
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'touch test.step'
                sh 'ls -l'
                sh 'mvn -B clean package'
            }
        }
    }
}
