node {
   stage('SCM Checkout') {
  git 'https://github.com/maheshwagh1402/webapp.git'

}
   stage('Build') {
     def mvn_version = tool name: 'Maven', type: 'maven'
      sh "{$mvnHome}/bin/mvn package"
}

    }
    stage('Package-Deploy') {
    sshagent(['tomcat-deploy']) {
    sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@172.31.16.100:/var/lib/tomacat8/webapps/'
}
}



}
