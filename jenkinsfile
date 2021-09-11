pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'MAVEN_HOME') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'MAVEN_HOME') {
                    sh 'mvn test'
                }
            }
        }


        stage ('Package Stage') {
            steps {
                withMaven(maven : 'MAVEN_HOME') {
                    sh 'mvn clean install'
                }
		    }
        }
		
	stage ('Deploy Stage') {
            steps {
        	    sh 'cp ./target/demo-0.0.1-SNAPSHOT.war /home/infogain/tomcat9/webapps/.'
                		
            }
        }
    }
}
