peline {
    agent any
    tools {
     nodejs 'NodeJS'
    } 
    stages {
        stage('Build') {
            steps {
                echo 'Compiling result app'
                dir('result'){
                    sh 'npm install'
                }
            }
        }
        stage('Test') {
          steps {
                when{
                   changeset "**/result/**"
                }
                dir('result'){
                   sh 'npm install'
                   sh 'npm test'
                }
            }
        }           
    }
}
