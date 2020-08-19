pipeline {
  agent any 
  tools {
    maven 'Maven'
  }
  stages {
    stage ('Initialize') {
      steps {
        sh '''
                echo "PATH = ${PATH}"
                echo "M2_HOME = ${M2_HOME}"
            ''' 
      }
    }
    stage ('Build') {
      steps {
      sh 'mvn clean package'
       }
    }   
    stage ('Deploy-To-Tomcat') {
       steps {
          sh 'sshpass -p 'toor' scp target/*.war root@192.168.56.101:/tomcat/apache-tomcat-8.5.57/webapps/webapp.war'     
       }       
    }
   }  
}
