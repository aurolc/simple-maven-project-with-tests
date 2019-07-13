pipeline {
   agent { label 'generic' }

   stages {
      stage('Build') {
         steps {
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
