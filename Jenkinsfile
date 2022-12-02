pipeline {
    agent {
        docker {
            image 'jenkins-node:latest'
            reuseNode true
            args '-v ${MAVEN_CONFIG}:/root/mavenrepo'
        }
    }È
    stages {
        stage('Build') {
            steps {
                sh 'ls -l'
                sh 'touch build.step'
                sh 'ls -l'
                sh 'printenv'
                sh 'echo ${env.WORKSPACE}'
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
