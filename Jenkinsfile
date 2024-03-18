pipeline
{
    agent any
    stages
    {
        stage('ContDownload')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/maven.git'
            }
        }
        stage('ContBuild')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('ContDeployment')
        {
            steps
            {
                deploy adapters: [tomcat9(credentialsId: '55f65faf-9892-486e-b1ad-d4ef79408c3a', path: '', url: 'http://172.31.20.244:8080')], contextPath: 'mytestapp', war: '**/*.war'
            }
        }
        stage('ContTesting')
        {
            steps
            {
            git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
           
            sh 'java -jar /var/lib/jenkins/workspace/DeclarativePipeline1/testing.jar'        
                
            }
        }
        stage('ContDelivery')
        {
            steps
            {
                input message: 'Need approval from DM!', submitter: 'srinivas'
                deploy adapters: [tomcat9(credentialsId: '55f65faf-9892-486e-b1ad-d4ef79408c3a', path: '', url: 'http://172.31.30.157:8080')], contextPath: 'myprodapp', war: '**/*.war'
            }
        }
        
        
        
        
    }
}
