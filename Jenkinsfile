
def mvnHome

node('node'){
   stage('git checkout'){
      try{
     git credentialsId: 'git-token', url: 'https://github.com/meteatbas/ci_cd_integration'
      }
      catch(err){
         sh "echo error in checkout"
      }
   }

   stage('maven test'){
      try{
         mvnHome=tool 'maven-3.6.3'
         sh "$mvnHome/bin/mvn --version"
         sh "$mvnHome/bin/mvn clean test surefire-report:report"
      }catch(err){
         sh "echo error in defining maven"
      }
   }

   // stage('test case and report'){
   //    try{
   //       echo "executing test cases"

   //    }
   // }
}