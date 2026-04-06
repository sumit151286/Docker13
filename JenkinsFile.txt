pipeline{
agent any
stages{
stage('1.checkout'){
steps{
git url : 'https://github.com/Aditya-Suresh25/docker-b3',branch:'main'
}
}
}
stage('2.Build Image'){
steps{
bat 'docker build -t Mywebsite .'
}
}
stage('3.Stop/Remove old Containers'){
steps{
bat 'docker stop mycont || exit 0'
bat 'docker rm mycont || exit 0'
}
}
stage('Run the Image - Containerize'){
steps{
bat 'docker run -d -p  5000:00 --name mycont MyWebsite'
}
}

}