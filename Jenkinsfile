pipeline {
    agent any

    tools {
        
        maven "maven-3.6.3"
    }

    stages {
        stage('Build') {
            steps {
               
                git branch: 'main', url: 'https://github.com/bbapplication/pluginapp.git'

                
                sh "mvn -Dmaven.test.failure.ignore=true clean package"

                
            }

            post {
                
                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                    archiveArtifacts 'target/*.jar'
                }
            }
        }
    }
}
