pipeline{
    agent any
    tools{
        jdk 'jdk17'
    }
     environment {
        SCANNER_HOME=tool 'sonar-scanner'
    }
    stages {
        stage('clean workspace'){
            steps{
                cleanWs()
            }
        }
        stage('Checkout from Git'){
            steps{
                git branch: 'main', changelog: false, poll: false, url: 'https://github.com/blessingmbatha/Netflix-clone.git'
            }
        }
        stage("Sonarqube Analysis "){
            steps{
                withSonarQubeEnv('sonar-server') {
                    sh ''' $SCANNER_HOME/bin/sonar-scanner -Dsonar.projectName=Netflix-clone \
                    -Dsonar.projectKey=Netflix-clone '''
                }
            }
        }
    }
   
}

