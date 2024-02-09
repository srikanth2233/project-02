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
    stage ('Deliver & Deployment') {
      sh 'curl -u ravi:ravi@777 -T target/**.war "http://54.82.83.135:80/manager/text/deploy?path=/ravi&update=true"'
  }
}
