pipeline {
  agent any
  stages {
    stage('Source') { 
      steps {
			// Some Step
	      
	      checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/chanchalsoni123/jenkins2-course-spring-boot.git']]])
      }
    }
def project_path ="spring-boot-samples/spring-boot-sample-atmosphere/"
dir(project_path)
	  {
    stage('Compile') { 
      tools {
        // Specify Tool Name from your global tool configuration
		jdk 'jdk8'
        maven 'apache-maven-3.6.1'
      }
      steps {
			// Some Step
	       powershell label: '', script: 'mvn clean package'
      }
    }
		  stage ('archival')
		  {
			  steps {
			  archiveArtifacts '**/*.jar'
			  
			  }
		  
		  }
		  
		 
		  
    }
  }
}
