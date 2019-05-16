node('linux'){
    stage('Unit Test'){
        git 'https://github.com/suyash776/java-project.git'
        sh 'ant -f test.xml -v'
        junit 'reports/*.xml'
    }
    
    stage('Build'){
        sh 'ant -f build.xml -v'
    }
    stage('Deploy'){
        sh 'echo deploy'
        sh 'aws s3 cp /workspace/java-pipeline/dist/rectangle-${BUILD_NUMBER}.jar s3:://seis66503-sshrestha'
    }
    
    stage('Results'){
       sh 'echo report'
    }
}
