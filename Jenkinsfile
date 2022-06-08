pipeline{
	agent any 
	stages{
		stage('1-git-clone'){
			steps{
				checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'Github-id', url: 'https://github.com/akudogithub/jenkins-parallel-job.git']]]) 
			}
		}
		stage('parallel-job'){
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
                stage('sub-job3'){
                    steps{
                        echo 'action3'
                        sh 'lscpu'
                        sh 'lsblk'
                    }
                }
                stage('sub-job4'){
                    steps{
                        sh 'cat /etc/passwd'
                        sh 'tail -10 /etc/passwd'
                    }
                }
			}
		}
		stage('3-code-build'){
			steps{
				sh 'sort -r /etc/passwd'
				sh 'ls -lrth /etc/passwd'
			}
		}
	}
}

