node {
   stage('SCM Checkout') {
  git 'https://github.com/maheshwagh1402/webapp.git'

}
   stage('Build') {
      def mvnHome=tool name: 'maven', type: 'maven'
      sh '${mvnHome}/mvn package'

    }
    stage('Package') {
    sshagent(['tomcat-deploy']) {
    sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@172.31.4.228:/opt/apache-tomcat-9.0.10/webapps/'
}
}



}
