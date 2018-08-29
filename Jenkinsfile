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
        sh 'cp target/*.war var/lib/tomacat8/webapps/'

}



}
