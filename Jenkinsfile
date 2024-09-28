pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/ashakumar87/bankproject12/'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with asha'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with asha'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with asha'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with asha'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t myimg .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8091:8091 --name c000 myimg'
            }
        }   
    }
}
