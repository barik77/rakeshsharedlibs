pipeline{
    agent any
    stages{
        stage("git chechout"){
        steps{
          git credentialsId: 'github-creds', url: 'https://github.com/lipun7/harisir.git'  
        }
    }
    stage("maven build"){
        steps{
sh 'mvn clean package -DskipTests=true'
        }
}
stages("Dev Tomcat Deploy"){
    steps{
        tomcatDeploy("172.31.1.213","ec2-user","tomcat-dev")
    }
}
}
