pipeline{
    agent {
      label 'localnode'
    }

    environment {
        name = "kiruba"
    }

    parameters {
        choice choices: ['one', 'two', 'three'], name: 'choice'
        string defaultValue: 'dharshini', name: 'lastname'
    }


    tools {
        maven 'mymaven'
    }

    stages{

        stage('Build Package') {

            steps {
                sh 'mvn clean package'
                echo "hello $name ${params.lastname}"
                echo "${params.choice}"
            } 
     
            post {
               success {
                   archiveArtifacts artifacts: '**/target/*.jar'
                }
            } 

        }

        stage('TEST') {
            parallel {
                stage('Test A') {
                    steps {
                        echo "hi test a"
                    }

                    steps{
                        echo "bye test a"
                    }
                }

                stage('Test B') {
                    steps {
                        echo "helo test b"
                     }
                }
            }   
        }
    }
}
        
