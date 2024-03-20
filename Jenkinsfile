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
        }

        stage('TEST') {
            parallel {
                stage('Test A') {
                    steps {
                        echo "hi test a"
                    }
                }

                stage('Test B') {
                    steps {
                        echo "helo test b"
                     }
                }
            }    

            post {
                success {
                    archiveArtifacts artifacts: '**/target/*.jar'
                }
            }   
   
        }
    }
}
        
