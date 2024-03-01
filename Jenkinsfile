pipeline {
    agent any
    stages {
        stage('Cloning') {
            steps {
                echo "Cloning from git"
                sh 'git clone https://github.com/microservices-demo/microservices-demo'
            }
        }
        stage('Build') {
            steps {
                echo 'Building the application...'
                mvn clean install
            }
        }
        stage('Tests') {
            steps {
                echo 'Running unit tests...'
                mvn test
            }
        }
        stage('Deploy to dev') {
      
            steps {
                echo 'Deploying to dev environment...'
                sh 'cd $WORKSPACE/microservices-demo/'
                sh 'kubectl apply -f manifests/'
            }
        }
    }
}

has context menu
