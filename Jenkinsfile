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
        stage("Test") {
            steps {
                echo("Hello Test")
            }
        }
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
        success {
            echo "Yay, success"
        }
        failure {
            echo "Oh no, failure"
        }
        cleanup {
            echo "Don't care success or error"
        }
    }
}
