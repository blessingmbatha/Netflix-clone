pipeline{
    agent any
    tools{
        jdk 'jdk17'
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
    }
   
}

