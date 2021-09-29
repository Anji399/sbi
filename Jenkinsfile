pipeline {
  agent any
    stages 
        {
	    stage('Clean') {
	          steps {
		          bat 'mvn clean'
			        }
				    }
				        stage('Compile') {
					      steps {
					              bat 'mvn compile'
						            }
							        }
								    stage('Test') {
								          steps {
									          bat 'mvn test'
										        }
											    }
											        stage('Deploy') {
												      steps {
												              bat 'mvn deploy'
													            }
														        }
															    stage('nexus') {
															          steps {
																          nexusArtifactUploader artifacts: [[artifactId: 'sbi', classifier: '', file: 'target/sbi.war', type: 'war']], credentialsId: '2448bd6a-2ecd-419b-a6f4-b3298223cd07', groupId: 'com.sbi', nexusUrl: 'localhost:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'sbi', version: '1.0-SNAPSHOT'
																	        }
																		    }
																		      }
																		      }
