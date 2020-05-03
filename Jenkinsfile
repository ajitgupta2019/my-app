pipeline {
    agent any 
    stages {
        		
		stage('clone_repo') { 
            steps {
            sh 'rm -fr my-app'
			sh 'git clone https://github.com/ajitgupta2019/my-app.git'		
		    dir("/var/lib/jenkins/workspace/MyFirstPipelineTest/my-app") {
            sh 'pwd'
            sh 'mvn clean'
		    }

            }
        }
      
        stage('Test') { 
            steps {
            dir("/var/lib/jenkins/workspace/MyFirstPipelineTest/my-app") {
             sh 'mvn test'
            }
            }
			}
		
		stage('Deploy') { 
            steps {
            dir("/var/lib/jenkins/workspace/MyFirstPipelineTest/my-app") {
             sh 'mvn package'
            }
            }
        }
    }
}
