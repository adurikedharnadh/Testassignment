pipeline {
    agent { label 'slave-1' }
    stages {
        stage('checkout') {
            steps {
                sh 'rm -rf hello-world-war'
                sh 'git clone https://github.com/shrikantashetty/hello-world-war.git'
            }
        } 
       stage('build') {
            steps {
                sh 'cd hello-world-war'
                sh 'mvn clean package'
            }
        }
      stage('deploy') {
           steps {
             sh 'cp /opt/jenkins/workspace/job_new2/target/hello-world-war-1.0.0.war /opt/apache-tomcat-10.1.34/webapps/hello-world-war-1.0.0.war'
               }
          }
    }
post {
    success {
        mail to: "adurikedharnadh@gmail.com",
             subject: "Jenkins Job Success",
             body: "The Jenkins job completed successfully."
    }
    failure {
        mail to: "adurikedharnadh@gmail.com",
             subject: "Jenkins Job Failed",
             body: "The Jenkins job failed. Check the logs for details."
    }
}
}
