#!groovy

node {
   stage 'Checkout'

   git url: 'https://github.com/rodrigozrusso/auto-versioning-lib-a.git'

   def mvnHome = tool 'maven3'

   stage 'Build'
   sh "${mvnHome}/bin/mvn clean compile"

   stage 'Packaging'
   sh "${mvnHome}/bin/mvn package"

   stage 'Archive'
   [$class: 'ArtifactArchiver', artifacts: 'target/auto-versioning-lib-a-*.jar', fingerprint: true]
}
