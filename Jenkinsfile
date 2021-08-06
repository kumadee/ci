pipeline {
    agent {
        label 'master'
    }
    stages {
        stage('build') {
            steps {
                echo "Build branch $BRANCH_NAME"
            }
        }
        stage('publish') {
            steps {
                echo "Publish commit - $GIT_COMMIT for branch - $GIT_BRANCH"
            }
        }
    }
}