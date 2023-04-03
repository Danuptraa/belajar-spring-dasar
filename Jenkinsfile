pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh './mvnw clean package'
            }
        }
        stage('Test') {
            steps {
                script {
                    def data = [
                        "firstName": "Muhamad Danu",
                        "lastName" : "Putra"
                    ]
                    writeJSON(file: "data.json", json: data)
                }
                echo("Start Test")
                sh  ('./mvnw test')
                echo("Finish Test")
            }
        }
        stage('Deploy') {
            steps {
                echo "Hallo Deploy"
                // sh './mvnw deploy'
            }
        }
    }

    post {
        always {
            echo "I will always say Hello again!"
        }
        success {
            echo "Yay, Success"
        }
        failure {
            echo "Oh no, failure"
        }
        cleanup {
            echo "Dont care succes or error"
        }
    }
}
