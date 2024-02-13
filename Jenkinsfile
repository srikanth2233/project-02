node {
   def mvnHome
  stage('Prepare') {
      git url: 'https://github.com/srikanth2233/project-02.git', branch: 'main'
      mvnHome = tool 'maven'
   }
    stage ('Clean') {
      sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean"
  }
    stage ('Validate') {
      sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore validate"
  }
    stage ('Compile') {
      sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore compile"
  }
    stage ('Test') {
      sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore test"
  }
    stage ('Package') {
      sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore package"
  }
    stage ('Verify') {
      sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore verify"
  }
    stage ('Install') {
      sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore install"
  }
    stage ('Deployment - Deloy a Artifact ravi-3.3.6.war file to Tomcat Server') {
      sh 'curl -u sri:sri@123 -T target/**.war "http://3.81.164.246:8080/manager/text/deploy?path=/srikanth&update=true"'
  }
}
