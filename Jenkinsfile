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
            powershell(script: 'docker images -a')
            powershell(script: """
                cd ci/
                docker build -t mybuild -f Dockerfile ..
                docker images -a
            """)
         }
      }
   }
}
