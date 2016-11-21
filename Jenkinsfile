
node{
	stage 'Checkout'
		echo 'Cloning Repo!'
		checkout scm
	
	stage 'Build'
		echo 'Testing'
		env.PATH = "${tool 'M3'}/bin:${env.PATH}"
		echo '111111111111111111111'
		sh 'pwd'
		sh 'ls'
		sh 'mvn clean'
		echo '--------------------No TARGET -----------------------------------'
		sh 'ls'
		sh 'mvn clean install'
		echo '--------------------Yes TARGET -----------------------------------'
		sh 'ls'
		sh ('cd target && ls')
	
	stage 'Deploy'
		sh 'cp target/*.jar /var/lib/jenkins/workspace/Deploy/'
		build job: 'Deploy'

	
}
