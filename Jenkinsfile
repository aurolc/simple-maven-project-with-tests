pipeline {
   agent { label 'generic' }

   tools {
        maven 'maven-3.6.1'
        jdk 'java-11'
    }

   stages {
      stage('Build') {
         steps {
            tool name: 'maven-3.6.1', type: 'maven'
            sh 'mvn -B -ntp -Dmaven.test.failure.ignore verify'
         }
      }

      stage('Junit') {
         steps {
            junit '**/target/surefire-reports/TEST-*.xml'
         }
      }
   }
}

