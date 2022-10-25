pipeline {
    agent any
    stages {
        stage('Test ansible version') {
            steps {
               ansiblePlaybook(
                    playbook: 'tomcat.yaml',
                    inventory: 'hosts', 
                    credentialsId: 'vm-ssh',
                    colorized: true 
                    )
                
            }
        }
        stage('Get Latest Artifacts') {
            steps {
               sh '''
               LATEST_ARTIFACT=`curl -s https://ibtlearning.jfrog.io//path/to/repository/ | grep -E hello-maven-[0-9\\.]+ | sed "s/<[^>]\\+>//g" | cut -d " " -f 1 | sort -V -r | head -n 1`
               wget https://ibtlearning.jfrog.io/artifactory/ibt-libs-snapshot-local/com/ibt/app/hello-maven/1.0-SNAPSHOT/$LATEST_ARTIFACT
               '''
        }
    }

}
