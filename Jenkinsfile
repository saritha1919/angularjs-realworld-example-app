pipeline {
         agent any
             stages {
	    
                 stage('Source') {
                    steps {
                       checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url:'https://github.com/saritha1919/angularjs-realworld-example-app.git']]])
			           }        
                 }
                  stage('Build') {
                            steps {  
                               powershell 'npm install'
                               powershell 'npm run build:ssr'
                               
                            }
                  }
                  stage('Deployment'){
			             steps{
				              powershell "pm2 restart all"
			             }
		           }
         }
}
