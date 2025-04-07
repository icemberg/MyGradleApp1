pipeline{
	agent any
	
	tools {
	    gradle 'Gradle'
	    jdk 'JDK'
	 }
	 stages {
		stage('Checkout') {
		    steps {
		        git branch: 'main', url: 'https://github.com/icemberg/MyGradleApp1.git'
		    }
		}

		stage('Build') {
		    steps {
		        sh 'gradle build'  // Run Maven build
		    }
		}

	       stage('Test') {
		   steps {
		       sh 'gradle test'  // Run unit tests
		   }
		}

		      
		stage('Run Application') {
		    steps {
		        // Start the JAR application
		        sh 'gradle run'
		    }
		}
           }

	    post {
		success {
		    echo 'Build and deployment successful!'
		}
		failure {
		    echo 'Build failed!'
		}
	    }
}
