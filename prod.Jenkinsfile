#!groovy

pipeline {
    agent {
         label 'master'
         }
    environment {
        GRADLE_OPTS='-Dorg.gradle.daemon=false'
    }
    options {
         timestamps()
    }
	  stages {
        stage("building an artifact") {
            steps {
			        withGradle {
              sh './gradlew war'
              }
            }
        }
	    	stage("testing an app") {
            steps {
			        withGradle {
              sh './gradlew check'
              }
            }
        }

    }
}
