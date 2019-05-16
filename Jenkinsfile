node('linux'){
    stage('Test'){
        git 'https://github.com/suyash776/java-project.git'
        sh 'ant -buildfile test.xml'
        sh 'echo here'
    }
    
    stage('Build'){
        sh 'ant'
    }
    
    stage('Results'){
        junit 'reports/*.xml'
    }
}
