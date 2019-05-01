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
        sh 'aws s3 cp /workspace/java-pipeline/dist/rectangle-${BUILD_NUMBER}.jar s3://seis66503-sshrestha/hw-10/rectangle-${BUILD_NUMBER}.jar'
 
    }
    stage('Report')
    {
        withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'aws-creds', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
            sh 'aws cloudformation describe-stack-resources --region us-east-1 --stack-name jenkins'
        }
     
    }
}
