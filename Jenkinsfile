pipeline {
    agent {
	node {
	  label "windows && java11"     
      }
    }
    
    stages {
        stage("Build") {
            steps {
                echo("Hello Build 1") 
                echo("Hello Build 2") 
                echo("Hello Build 3") 
                echo("Hello Build 4") 
            }
        }
        stage("Test") {
            steps {
                echo("Hello Test 1")
                echo("Hello Test 2")
                echo("Hello Test 3")
                echo("Hello Test 4")
            }
        }
        stage("Deploy") {
            steps {
                echo("Hello Deploy 1")
                echo("Hello Deploy 2")
                echo("Hello Deploy 3")
                echo("Hello Deploy 4")
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
