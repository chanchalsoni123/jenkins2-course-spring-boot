pipeline {
  agent any
  stages {
    stage('Source') { 
      steps {
			// Some Step
      }
    }
    stage('Compile') { 
      tools {
        // Specify Tool Name from your global tool configuration
		jdk 'jdk11'
        maven 'maven-3.6.1'
      }
      steps {
			// Some Step
      }
    }
  }
}
