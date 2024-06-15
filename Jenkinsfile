pipeline {
    agent any 
    stages {
        stage('Build') {
            steps {


                script {
                    def data:LinkedHashMap<String, String> = [
                        "firstName" : "Eko",
                        "LastName" : "Khanneddi"
                    ]
                }

                echo("Start Build")
                sh("./mvnw clean compile test-compile")
                echo("Finish Build")
            }
        }
        stage('Test') {
            steps {
                echo("Start Test")
                ("./mvnw test")
                echo("Finish test")
            }
        }
        stage('Deploy') {
            steps {
                echo("Hello Deploy 1")
                echo("Hello Deploy 2")
                echo("Hello Deploy 3")
            }
        }
    }


    post {
        always {
            echo "I will always say hello again"
        }
        success {
            echo "yay, success"
        }
        failure {
            echo "Oh no, Failure"
        }
        cleanup {
            echo "Don't care success or error"
        }
    }

}