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
               sh 'mvn clean install'
            }
        }
        stage('Deploy') 
        {
            agent {label "slave"}
            steps {
                
                sh 'ls'
                sh 'pwd'
                sh 'cp /opt/jenkins/workspace/job_new2/target/hello-world-war-1.0.0.war /opt/apache-tomcat-10.1.34/webapps/hello-world-war-1.0.0.war'
            }
        }
    }
}    
