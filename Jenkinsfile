properties([pipelineTriggers([githubPush()])])

node('linux') {
   stage('Test') {
       git 'https://github.com/vue07418/java-project.git'
       sh 'ant -buildfile test.xml'
   }
}
