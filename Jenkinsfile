//@Library('b2x-sharedlib-pipeline')_
pipeline {

    agent { node { label 'docker' } } 	
	
    environment { 
        http_proxy = 'http://fi001halti.ddc.teliasonera.net:8070'
        https_proxy = 'http://fi001halti.ddc.teliasonera.net:8070'
        no_proxy = "artifactory.verso.sonera.fi,127.0.0.1,localhost"
    }		

    tools { 
        nodejs 'nodejs10.15.0' 
    }
    stages {
        stage('Verify Code Style & Test-Coverage') {
            steps {
               //sendNotifications 'STARTED' 
               //sh 'git_branch_local=$(echo $GIT_BRANCH   | sed -e "s|origin/||g"); echo $git_branch_local;'
               echo "skipping this stage simply"
               /*sh '''
                npm install
                npm run verify-code-style
                npm run test-coverage
                npm run verify-test-coverage
                '''*/
            }

        }

        stage('Build & Deploy StoryBook') {

            when { changeRequest() }
                
            steps {
                sh '''
	              echo "Test for PR"                  
                '''
                }
            }        

    }
    post {
          always {
           //sendNotifications currentBuild.result
           echo "This is the always block"
          }
        }
}