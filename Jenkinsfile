#!groovy

node {
   stage 'Checkout'

   git url: 'https://github.com/rodrigozrusso/auto-versioning-lib-a.git'

   def mvnHome = tool 'maven3'

   stage 'Build'
   sh "${mvnHome}/bin/mvn clean package"

   stage 'Archive'
   [$class: 'ArtifactArchiver', artifacts: 'target/auto-versioning-lib-a-*.jar', fingerprint: true]
}
