CODE_CHANGES = getGitChanges()
pipeline {
   agent any
   parameters {
      string(name: 'VERSION', defaultValue: '', description: 'Version to deploy on prod')
      booleanParam(name: 'executeTests', defaultValue: true, description: '')
   }
   stages {
      stage("build") {
         when {
            expression {
               BRANCH_NAME == 'main' && CODE_CHANGES == true
            }
         }
         steps {
            echo "building the application"
         }
      }
      stage("test") {
         when {
            params.executeTests == true
         }
         steps {
            echo "testing the application"
         }
      }
      stage("deploy") {
         steps {
            echo "deploying the application"
            echo "deploying version ${params.VERSION}"
         }
      }
   }
   post {
      always {
         // 
      }
      success {
         //
      }
      failure {
         //
      }
   }
}
