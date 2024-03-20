pipeline{
    agent {
      label 'localnode'
    }
    stages{
        stage('Build Package') {
            sh 'mvn clean package'
        }   
    }
}
