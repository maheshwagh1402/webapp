node {
   stage('SCM Checkout') {
  git 'https://github.com/maheshwagh1402/webapp.git'

}
   stage('Build') {
     def mvn_version = 'Maven'
      withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] ) {
      sh "mvn clean package"
}
}
    stage('Package-Deploy') {
    sshagent(['tomcat-deploy']) {
    sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@172.31.16.100:/var/lib/tomacat8/webapps/'
}
}



}
