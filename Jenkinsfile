
pipeline {
    agent { label 'Build-2' }
    tools { 
        maven 'maven'
    }
    stages {
        stage('git checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Shreyas4321-s/war-web-project.git'
            }
        }
        stage('build') {
            steps {
                sh "mvn clean install"
            }
        }
        stage('deploy') {
            steps {
                sh "sudo cp /home/ec2-user/war-web-project/target/wwp-1.0.0.war /opt/tomcat/webapps"
            }
        }
    }
    post {
        success {
            echo "CICD pipeline succeeded"
        }
    }
}
