pipeline
{
    agent any
    stages {
        stage('Build') {
            agent {label "slave"}
            steps
            {
                sh 'rm -rf Testassignment'
             sh 'git clone https://github.com/adurikedharnadh/Testassignment.git'
            }
            
        }
        stage('Test') {
            agent {label "slave"}
            steps {
               sh 'cd Testassignment'
               sh 'mvn clean install'
            }
        }
        stage('Deploy') 
        {
            agent {label "slave"}
            steps {
                sh 'cd target'
                sh 'ls'
                sh 'pwd'
                sh 'cp hello-world-war-1.0.0.war /opt/apache-tomcat-10.1.34/webapps/'
            }
        }
    }
}    
