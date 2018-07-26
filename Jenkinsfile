node {
	echo "${params.story_id}"
	stage('Salesforce build'){
		echo "Building..."
		def branch_name='INT'
		checkout changelog: false, poll: false, scm: [$class: 'GitSCM', branches: [[name: '*/'+branch_name]], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'LocalBranch', localBranch: branch_name]], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'git-madepu-mirketa', url: 'https://github.com/madepu-mirketa/sp-poc.git']]]
		bat "git.exe merge origin/${params.story_id} && git.exe push origin ${branch_name}"
	}
	stage('Salesforce Predeploy Steps'){
		echo "Predeploy Steps"
	}
	stage('Salesforce Deploy Steps'){
		echo "Deploy Steps"
	}
	stage('Salesforce Post-Deploy Steps'){
		echo "Postdeploy Steps"
	}	
}