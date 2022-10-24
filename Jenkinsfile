pipeline {
    agent any
    stages {
        stage('Test ansible version') {
            steps {
               ansiblePlaybook( 
                    playbook: 'tomcat.yaml',
                    inventory: 'hosts', 
                    credentialsId: 'vm-ssh',
                    colorized: true) 
                }
            }
        }
    }

}
