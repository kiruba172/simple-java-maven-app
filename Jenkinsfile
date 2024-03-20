pipeline{
    agent {
      label 'localnode'
    }
    stages{
        stage('Build Package') {
            steps {
                sh 'mvn clean package'
            }
            
        }   
    }
}
