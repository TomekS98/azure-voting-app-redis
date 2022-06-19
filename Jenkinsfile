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
            pwsh 'Write-Output "test output"'
            pwsh 'docker images -a'
         }
      }
      

   }
}
