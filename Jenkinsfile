pipeline{
	agent any
	tools {
        maven 'MVN_HOME'
		jdk 'JDK_HOME'
    }
	stages{
		stage ('Initialize') {
            steps {
                bat '''
                    echo "M2_HOME = ${M2_HOME}"
					echo "JDK_HOME = ${JDK_HOME}"
                ''' 
            }
        }
		stage ('Clean workspace') {
            steps {
                deleteDir()
            }
        }
		stage ('Checkout from scm') {
            steps {
                checkout scm
            }
        }
		stage('clean-install stage'){
			steps{
					bat 'mvn -DskipTests clean install'
			}
		}
		stage('test stage'){
			steps{
					bat 'mvn test'
			}
		}
	}
}
