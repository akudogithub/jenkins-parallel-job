pipeline{
	agent any 
	stages{
		stage('1-git-clone'){
			steps{
				sh 'checkout'
			}
		}
		stage{
			parallel{
				stage('2-sub-job1'){
					steps{
						echo 'action1'
					}
				}
				stage('sub-job2'){
					steps{
						echo 'action2'
					}
				}
			}
		}
		stage('3-code-build'){
			steps{
				sh 'sort -r /etc/passwd'
				sh 'ls -lth /etc/passwd'
			}
		}
	}
}