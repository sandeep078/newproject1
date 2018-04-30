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
     stage('clean') {
      steps {
          sh 'mvn clean'
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
