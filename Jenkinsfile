pipeline {
  agent any
	stages {
    stage('Source') { 
      steps {
			// Some Step
	      
	      checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/chanchalsoni123/jenkins2-course-spring-boot.git']]])
      }
    }
    stage('Compile') { 
      tools {
        // Specify Tool Name from your global tool configuration
		jdk 'jdk8'
        maven 'apache-maven-3.6.1'
      }
      steps {
			// Some Step
	       powershell label: '', script: 'mvn -f spring-boot-samples/spring-boot-sample-atmosphere/pom.xml clean package'
      }
    }
		  stage ('archival')
		  {
			  steps {
			  archiveArtifacts '**/*.jar'
			  
			  }
		  
		  }
		
		stage ('Reports Generate')
		{
			steps{
			
			junit 'spring-boot-samples/spring-boot-sample-atmosphere/target/surefire-reports/*.xml'
				
				
			}
		}
		stage ('Reports Publish')
		{
		     steps
			{
			publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'spring-boot-samples/spring-boot-sample-atmosphere/target/site/jacoco', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: ''])
			}
		}
  }
}
