node('master') 
{
    stage('ContinuousDownload_Master') 
    {
         git 'https://github.com/Suryam2498/MyDevops.git'
        
    }
     stage('ContinuousBuild_Master') 
    {
        sh 'mvn package'
    }    
 }
