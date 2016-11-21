
node{
	stage 'Checkout'
		echo '------------------------- Cloning Repo! -------------------------'
		checkout scm
	
	stage 'Build'
		echo 'Testing'
		env.PATH = "${tool 'M3'}/bin:${env.PATH}"
		echo '------------------------- Removing target directory -------------------------'
		sh 'mvn clean'
		echo '------------------------- Maven Build -------------------------'
		sh 'mvn clean install'
	
	stage 'Deploy'
		echo '------------------------- Copying jar file to Deploy Workspace -------------------------'
		sh 'cp target/*.jar /var/lib/jenkins/workspace/Deploy/'
		echo '------------------------- Calling the Deploy Jenkins Job -------------------------'
		build job: 'Deploy'
	

}
