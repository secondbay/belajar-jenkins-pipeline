pipeline {
    agent none

    environment {
        JAVA_HOME = "/usr/lib/jvm/java-11-openjdk-amd64"
    }
    
    stages {
        stage("Prepare") {
            agent {
                node {
                    label "linux && java11"
                }
            }

            steps {
                echo("Start Job: ${env.JOB_NAME}")
                echo("Start Build: ${env.BUILD_NUMBER}")
                echo("Branch Name: ${env.BRANCH_NAME}")
            }
        }
        
        stage("Build") {
            agent {
                node {
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
                sh("./mvnw clean compile test-compile")  
                echo("Finish Build")  
            }
        }
        stage("Test") {
            agent {
                node {
                    label "linux && java11"
                    }
            }

            steps {
                script {
                    def data = [
                        'name':'Secondbay',
                        'age':'23',
                        'sallary':'Rp 7.000.000,00',
                        'job':'Devops Engineer'
                    ]

                    writeJSON(file: 'profile.json', json: data)
                }
                

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
