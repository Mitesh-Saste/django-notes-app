@Library("Library") _
pipeline{
    agent { label "mitesh"}
    
    stages{
        stage('Clone Code'){
            steps{
                script {
                    clone("https://github.com/Mitesh-Saste/django-notes-app.git","main")
                }
            }
        }
        stage('Build'){
            steps{
                script {
                    docker_build("notes-app","latest","miteshsaste")
                }
            }
        }
        stage('Push to DockerHub'){
            steps{
                script {
                    docker_push("notes-app","latest","miteshsaste")
                }
            }
        }
        stage('Deploy'){
            steps{
                echo "This is deploying the code"
                sh "docker compose up -d"
            }
        }
    }
}
