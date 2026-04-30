pipeline {
    agent none

    environment {
        JAVA_HOME = "/usr/lib/jvm/java-11-openjdk-amd64"
        PATH = "${JAVA_HOME}/bin:${env.PATH}"
    }
    
    stages {
        stage("Build") {
            agent{
                node{
                    label "linux && java11"
                }
            }

            steps {
                script {
                    for(int i = 0; i < 10; i++) {
                        echo("Script: ${i}")
                    }
                }
                
                echo("Start Build")
                sh("java -version")
                sh("./mvnw compile clean compile test-compile")  
                echo("Finish Build")  
            }
        }
        stage("Test") {
            agent{
                node{
                    label "linux && java11"
                }
            }

            steps {
                echo("Start Test")
                sh("./mvnw test")
                echo("Finish Test")
            }
        }
        stage("Deploy") {
            agent{
                node{
                    label "linux && java11"
                }
            }

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
