pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'export PATH=$PATH:/usr/local/in/npm'
                sh 'sudo npm install'
                sh 'sudo npm run build'
            }
        }
        stage('Deploy') {
            steps {
                sh 'sudo rm -rf /var/www/jenkins-react-app'
                sh "sudo cp -r ${WORKSPACE}/build/ /var/www/jenkins-react-app/"
            }
        }
    }
    tools { nodejs 'NodeJs' }  //name should be similar to name used for installer in the global tool configuration.
}
