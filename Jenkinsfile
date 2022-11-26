pipeline {
    agent {
        docker {
            image 'jenkins-node:9'
        }
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Build image') {
            steps {
                withKubeConfig([credentialsId: 'kube-config-file']) {
                    sh 'ytt -f image.yaml --data-value dockerusername=omocquais | kubectl apply -f -'
                    sh '/scripts/image-build-status.sh'
                }
            }
        }
    }
}
