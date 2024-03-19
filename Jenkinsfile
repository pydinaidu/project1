
pipeline{
    agent any
    tools {
        maven 'maven3'
    }
    stages{

        stage('Maven Build'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('Tomcat Deploy'){
            steps{
                library 'javahome-libs'
                tomcatDeploy credId: 'tomcat-dev',
                             ip: '173.23.45.78',
                             userName: 'ec2-user',
                             tomcatHome: '/opt/tomcat8',
                             warName: 'springmvc'
            }
        }
    }
}
