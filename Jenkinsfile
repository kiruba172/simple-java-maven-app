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
                   archiveArtifacts artifacts: '/home/kirubadharshini/jenkins/workspace/1stpipeline/target/*.jar'
                }
            } 

        }
    }
}
