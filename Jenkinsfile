pipeline {
    agent {
	node {
	  label "windows && java11"     
      }
    }
    
    stages {
        stage("Environment") {
            steps {
                sh("export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64")
                sh("export PATH=$JAVA_HOME/bin:$PATH")
            }
        }
        stage("Build") {
            steps {
                echo("Start Build")
                sh("./mvnw compile clean compile test-compile")  
                echo("Finish Build")  
            }
        }
        stage("Test") {
            steps {
                echo("Start Test")
                sh("./mvnw test")
                echo("Finish Test")
            }
        }
        stage("Deploy") {
            steps {
                echo("Hello Deploy 1")
                sleep(5)
                echo("Hello Deploy 2")
                echo("Hello Deploy 3")
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
