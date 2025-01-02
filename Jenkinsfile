pipeline
{
    agent any
    stages {
        stage('Build') {
            agent {label "slave"}
            steps
            {
             git clone https://github.com/adurikedharnadh/Testassignment.git
                
            }
            
        }
        stage('Test') {
            agent {label "slave"}
            steps {
               cd Testassignment
               mvn clean install
            }
        }
        stage('Deploy') 
        {
            agent {label "slave"}
            steps {
                cd target
                cp hello-world-war-1.0.0.war /opt/apache-tomcat-10.1.34/webapps/hello-world-war-1.0.0.war
            }
        }
    }
}    
