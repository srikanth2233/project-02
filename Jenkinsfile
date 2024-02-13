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
    stage ('Deployment') {
      sh 'curl -u sri:sri@123 -T target/**.war "http://34.227.98.165:8080/manager/text/deploy?path=/devops&update=true"'
  }
}
