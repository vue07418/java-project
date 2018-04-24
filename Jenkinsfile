properties([pipelineTriggers([githubPush()])])

node('linux') {
   stage('Unit Test') {
       git 'https://github.com/vue07418/java-project.git'
       sh 'ant -f test.xml -v'
   }
}
