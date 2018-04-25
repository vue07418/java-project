properties([pipelineTriggers([githubPush()])])

node('linux') {
   stage('Unit Test') {
       git 'https://github.com/vue07418/java-project.git'
       sh 'ant -f test.xml -v'
   }
   
   stage('Build') {
       sh 'ant -f build.xml -v'
   }
   
   stage('Deploy') {
       sh 'aws s3 cp /workspace/java-pipeline/dist/rectangle-*.jar s3://week-11-jenkins-javapipeline-assignment/rectangle-*.jar'
   }
   
   stage('Report') {
       sh 'aws cloudformation describe-stack-resources --region us-east-1 --stack-name jenkins'
   }
}
