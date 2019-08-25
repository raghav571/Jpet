  node {
    stages {
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
    stage("package") {
         sh 'mvn package'
       }
     }
    }
}
