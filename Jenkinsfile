pipeline{
agent  any
  stages{
    stage("checkout"){
      steps{
	      checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'git-tags', url: 'https://github.com/sriram-naresh/build-test-deploy-project.git']]])
      }
    }
     stage("Build"){
       steps{
         sh """
           mvn clean
           mvn install
         """
       }
     }
     stage("Test"){
       steps{
	  sh """
	     mvn test
	  """
      }
    }
  }
}
