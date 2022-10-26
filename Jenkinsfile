pipeline {
    agent any
    stages {
        stage('Configurae VM with Tomcat') {
            steps {
               ansiblePlaybook(
                    playbook: 'tomcat.yaml',
                    inventory: 'hosts', 
                    credentialsId: 'vm-ssh',
                    colorized: true 
                    )
                
            }
        }
//         stage('Get Latest Artifacts') {
//             steps {
//                sh '''
//                # Artifactory location
//                server=https://ibtlearning.jfrog.io/artifactory
//                repo=snapshot

//                # Maven artifact location
//                name=hello-maven
//                artifact=com/ibt/$name
//                path=$server/$repo/$artifact
//                version=$(curl -s $path/maven-metadata.xml | grep latest | sed "s/.*<latest>([^<]*)</latest>.*/1/")
//                build=$(curl -s $path/$version/maven-metadata.xml | grep '<value>' | head -1 | sed "s/.*<value>([^<]*)</value>.*/1/")
//                war=$name-$build.war
//                url=$path/$version/$war

//                # Download
//                echo $url
//                wget -q -N $url

//                '''
//             }
//         }
    }

}
