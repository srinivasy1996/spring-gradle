pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'gradle clean build'
            }
        }
        stage('Dockerize') {
            steps {
                sh 'docker build -t my-registry/my-spring-app:${VERSION} .'
                sh 'docker push my-registry/my-spring-app:${VERSION}'
            }
        }
    }
}
