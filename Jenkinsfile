pipeline {
   agent any

   stages {
      stage('Verify Branch'){
         steps {
            echo $GIT_BRANCH
         }
      }
      stage('Goodbye'){
         echo 'Goodbye World'
      }
      stage('pwsh Hello'){
         steps{
            poweshell label: '', script: 'Write-Output "Hello PowerShell!"'
         }
      }
   }
}
