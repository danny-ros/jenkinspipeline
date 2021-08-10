pipeline {
    agent any
    stages{
        stage('init'){
            steps {
                echo "Testing..."
            }
        }
    stages{
            stage('Build'){
                steps {
                    sh "mvn clean package"
                }
            }
    stages{
                stage('Deploy'){
                    steps {
                        echo "Code Deployed..."
                    }
                }
    }
}

