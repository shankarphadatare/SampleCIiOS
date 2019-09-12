pipeline {
    agent any 
    stages {
        stage('One') {
            steps {
                echo 'Hi, this is shankar'
            }
        }
        stage('Two') {
            steps {
                input('Do you want to proceed?')
            }
        }
    }
}
