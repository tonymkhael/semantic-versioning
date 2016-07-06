node {
    
   // Mark the code checkout 'stage'....
   stage 'Checkout'

   // Get the code from the Stash repository
   checkout scm

   // Mark the code build 'stage'....
   stage 'Build'
   
   // Make sure script is runnable
   sh "chmod a+x ./gradlew"
   
   // Run gradle build and deploy
   wrap([$class: 'ConfigFileBuildWrapper', managedFiles: [[fileId: 'org.jenkinsci.plugins.configfiles.custom.CustomConfig1453803770046', replaceTokens: false, targetLocation: 'gradle.properties', variable: '']]]) {
    sh "./gradlew snapshot asciidoctor"
   }
   
}