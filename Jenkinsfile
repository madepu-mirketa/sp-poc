node {
	stage('Salesforce build'){
		echo "Building..."
		def branch_name='INT'
		checkout changelog: false, poll: false, scm: [$class: 'GitSCM', branches: [[name: '*/'+branch_name]], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'git-madepu-mirketa', url: 'https://github.com/madepu-mirketa/sp-poc.git']]]
	}
	stage('Salesforce deploy'){
		echo "Deploy..."
	}
}