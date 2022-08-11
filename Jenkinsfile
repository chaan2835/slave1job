pipeline {
	
	agent any 

		stages{
				stage ('build'){
					
							steps {
							
							sh 'mvn clean package'
					       			}
						}
				stage ('artifact upload') {
							
							steps {
								nexusArtifactUploader artifacts:
								[
									[
										artifactId: 'javaparser-core', 
										classifier: '', file:'target/javaparser-maven-sample-1.0-SNAPSHOT-shaded.jar', 
										type: 'jar'
									]
								], 

								credentialsId: 'b4b22ac4-cc33-444a-a50c-945f6eb4edc8',
								groupId: 'com.github.javaparser',
								nexusUrl: '172.31.33.156:8081',
								nexusVersion: 'nexus3',
								protocol: 'http',
								repository: 'CR-1.1.1',
								version: '3.23.1'
								}
							}
						}
					}
