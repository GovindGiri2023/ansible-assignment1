pipeline{
	agent{
		label{
			label "built-in"
		}
	}
	tools{
	   ansible "ansible"
	}

	stages{
		stage("clean workspace"){
			steps{
				cleanWs()
			}
		}
		stage("checkout from scm"){
			steps{
				checkout scm
			}
		}
		stage("check ansible version"){
			steps{
				sh "ansible --version"
			}
		}
	}

	
}
