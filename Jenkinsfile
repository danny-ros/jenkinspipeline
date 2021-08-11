pipeline {
    agent {
        label 'master'
    }
    
    stages{
        stage('checkout code'){
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/danny-ros/jenkinspipeline.git']]])
            }
        }
        stage('Build'){
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy to Integration ') {
            steps {
                sh 'cp webapp/target/webapp.war /opt/tomcat/latest/webapps'
            }
        }
        stage('Archive Artifact  ') {
            steps {
                archiveArtifacts artifacts: 'webapp/target/webapp.war', followSymlinks: false
            }
        }    
    }
}
