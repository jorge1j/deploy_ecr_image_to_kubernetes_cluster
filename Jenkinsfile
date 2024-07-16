pipeline{
    agent any 
    tools{
        maven "Maven_3_5_2"   
    }
   stages{
         stage('CompileandRunSonarAnalysis') {
             steps {	
		    withCredentials([string(credentialsId: 'SONAR_TOKEN', variable: 'SONAR_TOKEN')]) {
   sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=geeteck1 -Dsonar.organization=geeteck1 -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=$SONAR_TOKEN'
}

		
 	//		}
//         } 
//	    stage('RunSCAAnalysisUsingSnyk') {
  //          steps {		
//				withCredentials([string(credentialsId: 'SNYK_TOKEN', variable: 'SNYK_TOKEN')]) {
//					sh 'mvn snyk:test -fn'
//				}
//			}
//    }	
//        stage('Build'){
//            steps{
//                withDockerRegistry(
 //                   [credentialsId:"dockerlogin", url: ""]
  //              )  {
    //                script{
     //               app = docker.build("asg")
   //                 }
                }
       //     }
        //}

        //stage('Push'){
          //  steps{
            //    script{
              //      docker.withRegistry("https://924338258393.dkr.ecr.us-east-1.amazonaws.com", "ecr:us-east-1:aws-credentials"){
                //        app.push("latest")
                  //  }
                    
                    
                }
            }
        }

    
     stage('Kubernetes Deployment of Easy Buggy Web Application') {
	   steps {
	      withKubeConfig([credentialsId: 'kubelogin']) {
		  sh('kubectl delete all --all -n devsecops')
		  sh ('kubectl apply -f deployment.yaml --namespace=devsecops')
		    }
	      }
        	}
    
     }    
    
}
