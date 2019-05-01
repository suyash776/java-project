node('linux'){
    stage('Unit Test')
   {
        git 'https://github.com/suyash776/java-project.git'
        sh 'ant -f test.xml'
        junit 'reports/result.xml'
    }
    stage('Build')
    {
        sh 'ant -f build.xml -v'
    }
    stage('Deploy')
    {
        sh 'echo ${BUILD_NUMBER}'
        sh 'echo rectangle-${BUILD_NUMBER}.jar'
        sh 'aws cp /workspace/java-pipeline/dist/rectangle-${BUILD_NUMBER}.jar s3://seis66503-sshrestha/rectangle-${BUILD_NUMBER}.jar'
 
    }
}
