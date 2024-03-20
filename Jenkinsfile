pipeline{
    agent {
      label 'localnode'
    }

    tools {
        maven 'mymaven'
    }

    stages{

        stage('Build Package') {

            steps {
                sh 'mvn clean package'
            } 

            post {
               success {
                   archiveArtifacts artifacts: '**/target/*.jar'
                }
            } 

        }
    }
}
