pipeline {

agent { label 'linux-agent-1' }

	tools 
	{ 
	maven "M2_HOME"
	jdk "jdk 1.8"
	}

stages {
	//stage("cloning from git")
	//{
	//steps { git credentialsId: 'Maven-Jar', url: 'https://github.com/Balameenakshi/Sample-maven-war-app.git' }
	//}

	stage("Build using Maven")
	{
	steps { 
	sh '"/usr/bin/mvn" -Dmaven.test.failure.ignore clean package' }
	}

	stage("Results")
	{
	steps { archiveArtifacts 'target/*.war' }
	}
}

}
