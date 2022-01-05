pipeline {
    agent any

    tools {
	maven 'Maven-3.8.4'
        
    }

    stages {
       
	   stage('Maven Version') {
            steps {
			  sh 'mvn --version'
            }
        }
		stage('Git Clone') {
            steps {
			 git credentialsId: 'git', url: 'https://github.com/kartikeyapro/ks.git'
            }
        }		
		
		stage('Maven Clean') {
            steps {
			  sh 'mvn clean'
            }
        }
			stage('Maven Validate') {
            steps {
			  sh 'mvn validate'
            }
        }
			stage('SonarScan') {
            steps {
			  sh 'mvn sonar:sonar -Dsonar.host.url=http://34.68.2.232:9000 -Dsonar.login=c03b084c29bdf53c6a033069a53c5616802692b8'
            }
        }
			stage('Maven Compile') {
            steps {
			  sh 'mvn compile'
            }
        }
			stage('Maven Test') {
            steps {
			  sh 'mvn test'
            }
			
        }
			stage('Maven Package') {
            steps {
			  sh 'mvn package'
            }
			
        }
			stage('Maven deploy') {
            steps {
			  sh 'mvn deploy'
            }
			
        }
		
		
}
}
