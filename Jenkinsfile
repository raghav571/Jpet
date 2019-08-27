node {
    stage("Checkout") { 
      // Get some code from a GitHub repository
      git 'https://github.com/raghav571/jpet.git'
      // Get the Maven tool.
      // ** NOTE: This 'M3' Maven tool must be configured
      // **       in the global configuration.           
      }
   env.JAVA_HOME = "${'/opt/jdk1.8.0_131'}"
   env.PATH = "${env.JAVA_HOME}/bin:${env.PATH}"
   sh 'java -version' 
   
   env.M2_HOME = "${'/opt/apache-maven-3.6.0/'}"
   env.PATH = "${env.M2_HOME}/bin:${env.PATH}"
   sh 'mvn -version'
    
   stage("Compile") {
            sh 'mvn compile'
        }
   
   stage("package") {
         sh 'mvn package'
       }
   
   stage("Deployment Check") {
         input 'Deploy to Production?'
       }
    
   stage("Deploy") {
         //deploy contextPath: null, onFailure: false, war: 'ubuntu@54.175.109.197:/opt/apache-tomcat-7.0.96/webapps -u ubuntu -p root'
         //sh 'cd /var/lib/jenkins/workspace/Scripted-Pipeline/target'
         //deploy adapters: [tomcat7(credentialsId: '4e201b56-24eb-4f06-b184-d780b8654784', path: '', url: 'https://3.87.216.51:8080')], contextPath: null, war: '**/*.war'
         //withCredentials([usernameColonPassword(credentialsId: '6ff492ce-520f-4682-b3d4-93ec87cd4c31', variable: '')]) {
         // some block
         //sh 'scp /var/lib/jenkins/workspace/Scripted-Pipeline/target/*.war ubuntu@54.161.111.216:/opt/apache-tomcat-7.0.96/webapps'
         //input 'Enter Password'       
         //input message: 'enter password', parameters: [password(defaultValue: 'value', description: '', name: 'hidden')]
         //input message: 'enter password'
         deploy adapters: [tomcat7(credentialsId: '4e201b56-24eb-4f06-b184-d780b8654784', path: '', url: 'http://54.161.111.216:8080')], contextPath: null, war: '**/*.war'      
   }    
     }
}
