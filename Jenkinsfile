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
		stage("checkout frm scm"){
			steps{
				checkout scm
			}
		}
		
	}

	
}
