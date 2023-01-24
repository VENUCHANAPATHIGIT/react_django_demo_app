pipeline {
    agent any 
    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/VENUCHANAPATHIGIT/react_django_demo_app.git'
            }
        }
        stage('Docker build') {
            steps {
                sh 'docker build -t myapp .'
            }
        }
        stage('Docker run') {
            steps {
                sh 'docker run -d --name myappone -p 8001:8001 myapp'
            }
        }
        stage('Removing docker images') {
            steps {
                sh 'docker stop myappone'
                sh 'docker rm myappone'
                sh 'docker rmi myapp'
            }
        }
    }
}
