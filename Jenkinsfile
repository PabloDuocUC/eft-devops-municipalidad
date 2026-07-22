pipeline {
    agent any
    environment {
        IMAGE     = 'usuarios-rest'
        CONTAINER = 'usuarios-app'
    }
    stages {
        stage('1. Checkout') {
            steps { checkout scm; sh 'ls -la' }
        }
        stage('2. Build Maven') {
            steps { sh 'mvn -B clean package -DskipTests'; sh 'ls -lh target/*.war' }
        }
        stage('3. Docker Image') {
            steps { sh 'docker build -t $IMAGE:$BUILD_NUMBER -t $IMAGE:latest .' }
        }
        stage('4. Deploy Container') {
            steps {
                sh 'docker rm -f $CONTAINER || true'
                sh 'docker run -d --name $CONTAINER -p 8081:8080 $IMAGE:latest'
                sh 'docker ps'
            }
        }
        stage('5. Verify') {
            steps { sh 'sleep 25'; sh 'curl -i http://localhost:8081/usuariosBuild/user || true' }
        }
    }
}