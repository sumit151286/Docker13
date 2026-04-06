pipeline{
  agent any
  stages{
    stage('checkout'){
      steps{
        git url:https://github.com/sumit151286/Docker13/new/main
          }
    }

          stage{'Build Image'}{
            steps{
              bat'docker build -t myimg -'
          }
          }
          
          stage('3.Stop/Remove old container'){
            steps{
              bat 'docker stop mycount || exit0'
               bat 'docker rm mycount || exit0'
          }
          }
          stage("Run the Image- Containerize'){
                steps{
                  bat 'docker run -d -p 5000:80 --name mycount myimg'
                }
                }

                }
                }
