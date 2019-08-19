node {
stage("scm"){
git 'https://github.com/ghanigreen/maven_demo.git'
}
stage("unittest"){
sh 'mvn test'
}
stage("build"){
sh 'mvn verify'
}
stage("sonarqube")
sh 'mvn sonar:sonar'
stage("testresults")
junit '**/gameoflife-core/target/surefire-reports/*.xml'
stage("archiveartifacts")
archiveArtifacts '**/*.war'
stage("Deployment")
sh label: '', script: 'cp -R /var/lib/jenkins/workspace/anitha_pipeline/gameoflife-web/target/gameoflife.war /opt/tomcat/apache-tomcat-9.0.17/webapps/'
}


/** Windows copy 
cd C:/PalaJenkins/18Aug2019/target
set CATALINA_HOME="C:/Program Files/Apache Software Foundation/Tomcat 9.0"
copy demoemployee-0.0.1-SNAPSHOT.war %CATALINA_HOME%\webapps
**/