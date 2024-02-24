node('built-in') 
{
 stage('ContinuousDownloads') 
 {
    git 'https://github.com/atuldevpandey/maven45.git'
 }
 stage('ContinuousDownloads') 
 {
    sh 'mvn package'
 }
 stage('ContinuousDeployment') 
 {
    deploy adapters: [tomcat9(credentialsId: 'ed40dadb-5c30-4895-9190-09697e742f20', path: '', url: 'http://172.31.43.138:8080')], contextPath: 'testapp', war: '**/*.war'
 }
 stage('ContinuousTesting') 
 {
    git 'https://github.com/atuldevpandey/FunctionalTesting.git'
    sh 'java -jar /home/ubuntu/.jenkins/workspace/scriptedPipeline/testing.jar'
 }
  stage('ContinuousDelivery') 
 {
    deploy adapters: [tomcat9(credentialsId: 'ed40dadb-5c30-4895-9190-09697e742f20', path: '', url: 'http://172.31.44.220:8080')], contextPath: 'prodapp', war: '**/*.war'
 }
}
