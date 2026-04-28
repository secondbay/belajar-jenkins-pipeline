pipeline {
    agent {
	node {
	  label "windows && java11"     
      }
    }
    
    stages {
        stage("Hello") {
            steps {
                echo("Hello Pipeline") 
            }
        }
    }
}
