node('linux'){
    stage('Test')
    steps{
        git 'https://github.com/suyash776/java-project.git'
        sh 'ant -buildfile test.xml'
    }
    stage('Build')
    steps{
        sh 'ant'
    }
    stage('Results')
    steps{
        junit 'reports/*.xml'
    }
}
