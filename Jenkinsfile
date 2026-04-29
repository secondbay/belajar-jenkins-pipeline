pipeline {
    agent {
	node {
	  label "windows && java11"     
      }
    }
    
    stages {
        stage("Build") {
            steps {
                echo("Hello Build") 
            }
        }
    }

    stages {
        stage("Test") {
            steps {
                echo("Hello Test")
            }
        }
    }

    stages {
        stage("Deploy") {
            steps {
                echo("Hello Deploy")
            }
        }
    }

    post {
        always {
            echo "i will always say hello again!"
        }
    }
}
