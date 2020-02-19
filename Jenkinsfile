pipeline {
    agent any
    environment{
      AWS_ACCOUNT=753025320351
      REPO_NAME="ci_api-v2.higg.org-development"
      AWS_REGION="us-west-2"
      ECR_REPO="${AWS_ACCOUNT}.dkr.ecr.${AWS_REGION}.amazonaws.com/${REPO_NAME}"
      ECR_TAG="${BUILD_ID}"
    }
    stages{
        stage('Check for CHANGELOG update') {
            steps {
                sh '''
                    set +x
                    echo '*******************************************************************************************'
                    echo '***********************    DEPLOY INFORMATION    ******************************************'
                    echo '*******************************************************************************************'
                    
                    echo BRANCH TO DEPLOY: ${DEPLOYED_BRANCH}
                    
                    echo COMMIT: ${GIT_COMMIT}

                    echo '*******************************************************************************************'
                    echo '***********************        CHANGELOG    ***********************************************'
                    echo '*******************************************************************************************'

                    git log ${GIT_PREVIOUS_COMMIT}..${GIT_COMMIT} --oneline
                    
                    echo '*******************************************************************************************'
                    echo '***********************   END OF INFORMATION   ********************************************'
                    echo '*******************************************************************************************'
                '''
            }
        } 
        stage('Test') {
            stage('Test app') {
                steps {
                    sh '''
                    set -ex

                    echo "add test here later"
                    '''
                }
            }
        }
    }
}
