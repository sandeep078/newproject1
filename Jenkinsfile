pipeline {
  agent any

 options {
  buildDiscarder(logRotator(numToKeepStr: '1', artifactNumToKeepStr: '1')) 
}


  stages {
   stage('build') {
      steps {
          sh 'mvn install'
           }
}
     stage('install') {
      steps {
          sh 'mvn install'
            }
}

  stage('docker step') {
      steps {
          sh 'sudo docker pull centos'
           }

}

}
	post {
	always {
archiveArtifacts artifacts: 'add/target/*.jar', fingerprint: true
archiveArtifacts artifacts: 'sub/target/*.jar', fingerprint: true
}
}
}
