@Library("shared") _ 
pipeline{
    agent {label "vinod"}
    stages{
        stage("hello "){
            steps{
                script{
                    hello()
                }
            }
        }
        stage("code"){
            steps{
                script{
                 clone("https://github.com/Yas19-bit/django-notes-app.git","main")
                }
            }
        }
        stage("build"){
            steps{
                script{
                    docker_build("notesapp","latest","yashgandhi19")
                }
              
            }
        }
      
        stage("push"){
            steps{
                script{
                docker_push("notesapp","latest","yashgandhi19")
                    
                }
                
            }
        }
        stage("deploy"){
            steps{
                echo "deployment hoving"
                sh "docker run -d -p 8000:8000 notesapp:latest"
            }
        }
    }
}
