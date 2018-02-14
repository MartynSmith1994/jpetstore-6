pipeline 
{
    agent any
    tools
    {
        maven "maven-3.5.2"
    }
    stages 
    {
        stage('Build') 
        {
            steps 
            {
                echo 'Building..'
                sh 'mvn clean verify'
            }
       
        }
        stage('Test') 
           {
           steps 
                {
                    echo 'Testing..'
                    junit 'target/surefire-reports/*.xml'
                 }
            }
        stage('Deploy') 
        {
            steps 
            {
                echo 'Deploying....'       
                withCredentials([sshUserPrivateKey(credentialsId: 'e731d4d6-5cfc-4cfb-a557-869770d27a6a', keyFileVariable: 'sshVar', passphraseVariable: '', usernameVariable: 'ubuntu')]) {
                    sh 'scp /Users/Shared/Jenkins/Home/workspace/useCaseTest/target/jpetstore.war http://52.212.53.70:/opt/apache-tomcat-9/webapps/'
                }
                
                echo 'Deployed.'
            }
        }
    }
}
