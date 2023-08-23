pipeline {
	agent any
	environment {
		mavenHome = tool 'jenkins-maven'
	}
	tools {
		jdk 'java-17'
	}
	stages {
		stage('Build'){
			steps {
				bat 'echo "Building"'
				bat "mvn clean install -DskipTests"
			}
		}
		stage('Test'){
			steps{
				bat 'echo "Testing"'
				bat "mvn test"
			}
		}
		stage('Deploy') {
			steps {
			    bat 'echo "Deploying"'
			    bat "mvn jar:jar deploy:deploy"
			}
		}
	}
}
