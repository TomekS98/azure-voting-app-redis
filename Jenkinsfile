pipeline {
   agent any

   stages {
      stage('Verify Branch') {
         steps {
            echo "$GIT_BRANCH"
         }
      }
      stage('Docker Build') {
         steps {
            bat 'cd azure-vote/'
            bat 'powershell.exe docker build -t jenkins-pipeline .'
            bat 'powershell.exe docker images -a'
            bat 'cd ..'
         }
      }
      stage('Start test app'){
         steps {
            bat """
            powershell.exe ./scripts/test_container.ps1
            """
         }
         post{
            success {
               echo "App started successfully"
            }
            failure {
               echo "App failed to start"
            }
         }
      }
      stage('Run Tests'){
         steps {
            bat """
            powershell.exe pytest ./tests/test_sample.py
            """
         }
      }
      stage('Stop test app'){
         steps {
            bat """
            powershell.exe docker-compose down
            """
         }
      }
      

   }
}
