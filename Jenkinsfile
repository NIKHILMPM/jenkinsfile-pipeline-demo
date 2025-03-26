pipeline{
agent any
  tools{
     maven 'mymaven'
  }

stages{
stage('clone Repo')
  {
    steps{
       git 'https://github.com/Sonal0409/DevOpsCodeDemo.git'     
    }
  }
stage('Build Code')
  {
    steps{
       sh 'mvn package'   
    }
  }

stage('Deploy Code')
  {
    steps{
      deploy adapters: [tomcat9(credentialsId: 'tomcatcredentials', path: '', url: 'http://3.82.197.118:9090/')], contextPath: null, war: '**/*.war'
    }
  }
}

  
}
