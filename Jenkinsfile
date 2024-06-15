pipeline {
    agent none 
    stages {
        stage('Prepare') {
            steps {
                echo("Start Job : ${env.JOB_NAME}")
                echo("Start Bulild : ${env.JOB_NUMBER}")
                echo("Start Name : ${env.BRANCH_NAME}")
            }
        }
        stage('Test') {
            steps {

                 script {
                    def data = [
                        "firstName" : "Eko",
                        "LastName" : "Khanneddi"
                    ]
                    writeJSON(files: "data.json", json: data)
                }
                 
                echo("Start Test")
                sh("./mvnw test")
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