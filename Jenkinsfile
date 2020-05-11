node {
  
    docker.withRegistry('https://192.168.1.15:5000', 'gaiden1594') {
        image = docker.image('emie_after_deploy')
        image.pull()
        docker.image('emie_after_deploy').inside("-u root --entrypoint=''") {

		stage('Git Pull'){
			sh 'git stash'
                        sh 'git pull https://kyriakos1594:gaiden1594@github.com/kyriakos1594/test.git master'
                        sh 'git checkout master'
		}

		stage('Deploy'){ 
                        sh 'git checkout production'
                        sh 'git merge master'
			sh 'git push -u https://kyriakos1594:gaiden1594@github.com/kyriakos1594/test.git production'
		}

	}
    }
}
