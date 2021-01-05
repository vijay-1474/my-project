node('master') 
{
    stage('ContinuousDownload_Master') 
    {
         git 'https://github.com/Suryam2498/MyDevops.git'
    }
     stage('ContinuousBuild_Master') 
    {
        sh label: '', script: 'mvn package'
    }
    stage('ContinuousDeployment_Master')
    {
        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.26.156:/var/lib/tomcat9/webapps/sur_QA.war'
    }
    stage('ContinuousTesting_Master')
    {
        git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
        sh label: '', script: 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline/testing.jar'
    }
     stage('ContinuousDelivery_Master')
    {
        //input message: 'Waiting for Approval from the DM!', submitter: 'srinivas'
        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.29.108:/var/lib/tomcat9/webapps/Sur_prod.war'
    }
    
 
}
