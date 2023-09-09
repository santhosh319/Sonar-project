pipeline{
    agent any
    environment {
        PATH = "$PATH:/root/apache-maven-3.9.4/bin"
    }
    stages{
       stage('Checkout'){
            steps{
                git 'git@github.com:NagiReddyDEVOPS/Sonar-Project.git'
            }
         }        
       stage('Package'){
            steps{
                sh 'mvn clean package'
            }
         }
        stage('SonarQube analysis') {
//    def scannerHome = tool 'SonarScanner 4.0';
        steps{
        withSonarQubeEnv('SonarQube') { 
        // If you have configured more than one global server connection, you can specify its name
//      sh "${scannerHome}/bin/sonar-scanner"
        sh "mvn clean verify sonar:sonar -Dsonar.projectKey=sonarfinal -Dsonar.host.url=http://65.2.71.140:9000 -Dsonar.login=sqp_18343188dc0e53b9857582e6d3c997f89f88b9a1"
    }
        }
        }
       
    }
}
