node('linux'){
    stage('Unit Test')
   {
        git 'https://github.com/suyash776/java-project.git'
        sh 'ant -f test.xml'
        junit 'reports/result.xml'
    }
    stage('Build')
    {
        sh 'ant -f build.xml' -v
    }
}
