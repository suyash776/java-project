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
        sh 'aws cp /workspace/java-pipeline/dist/rectangle-*.jar s3://seis66503-sshrestha/'
    }
}
