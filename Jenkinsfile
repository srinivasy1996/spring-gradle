pipeline {
    agent any {
        tools {
            gradle 'gradle-7.2'
        }
    }
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
