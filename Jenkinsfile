node {

	def story_list= "${params.story_list}"
	def branch_list="${params.branch_list}"
	echo "${story_list}"
	echo "${branch_list}"	
	stage('Salesforce build'){
		echo "Building..."
		def branch_name='INT'
		checkout changelog: false, poll: false, scm: [$class: 'GitSCM', branches: [[name: '*/'+branch_name]], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'LocalBranch', localBranch: branch_name]], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'git-madepu-mirketa', url: 'https://github.com/madepu-mirketa/sp-poc.git']]]
		
		branch_list.split(',').each{ aBranch ->
			echo "git merge origin/${aBranch}"
			if(isUnix()){
				sh "git merge origin/${aBranch}"
			}
			else{
				bat "git.exe merge origin/${aBranch}"
			}
		}
		if(isUnix()){
			sh "git push origin ${branch_name}"
		}
		else{
			bat "git.exe push origin ${branch_name}"
		}
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