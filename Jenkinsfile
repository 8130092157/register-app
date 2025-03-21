pipeline {
    agent { label 'j-node' }
    tools {
        jdk 'Java17'
        maven 'Maven3'
    }
    stages {
        stage("Cleanup Workspace"){
            steps {
                cleanWs()
            }
    }
        stage("Checkout from SCM"){
            steps {
                git branch: 'main', credentialsID: 'github', url: 'https://github.com/8130092157/register-app'
            }
        }
        stage("Build Application"){
            steps {
                sh "mvn clean package"
            }
        }
        stage("Test Application"){
            steps {
                sh "mvn test"
            }
        }      
    }       
}
