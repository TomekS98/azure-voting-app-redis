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
            bat 'powershell.exe Write-Output "test output"'
            bat 'powershell.exe docker images -a'
         }
      }
      

   }
}
