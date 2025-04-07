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
		        sh './gradlew build'  // Run Maven build
		    }
		}

	       stage('Test') {
		   steps {
		       sh './gradlew test'  // Run unit tests
		   }
		}

		      
		stage('Run Application') {
		    steps {
		        // Start the JAR application
		        sh './gradlew run'
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
