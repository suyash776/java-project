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
    }
    
    stage('Results'){
       sh 'echo report'
    }
}
