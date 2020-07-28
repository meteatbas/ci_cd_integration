
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
         sh "$mvn.Home/bin/mvn --version"
         sh "$mvn.Home/bin/mvn clean test surefire-report:report"
      }catch(err){
         sh "echo error in defining maven"
      }
   }
}