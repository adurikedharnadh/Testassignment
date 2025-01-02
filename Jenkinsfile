pipeline {
    agent { label 'slave' }
    stages {
        stage('checkout') {
            steps {
                sh 'rm -rf Testassignment'
                sh 'git clone https://github.com/adurikedharnadh/Testassignment.git'
            }
        } 
       stage('build') {
            steps {
                sh 'cd Testassignment'
                sh 'mvn clean package'
            }
        }
}
}
