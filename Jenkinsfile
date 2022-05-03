pipeline {
	agent any 
	stages{
		stage('One'){
			steps {
				echo "hello ! This is krishna vamshi"
			}
		}
		stage('Two'){
			steps {
				input('Do you want to peoceed ?')
			}
		}
		stage('Three'){
			when{
				not {
					branch "master"
				}
			}
			steps {
				echo "Hello"
			}
		}
		stage('Four'){
			parallel {
				stage('Unit Test'){
					steps{
						echo 'running unit test'
					}
				}
				stage('Integration Test'){
					agent  {
						docker {
							reuseNode false
							image 'ubuntu'
						}
				
					}
					steps {
						echo "Running the integration test"
					}
				}
			}
		}
	}
}