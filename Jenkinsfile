pipeline {
    agent {
        label 'master'
    }
    stages {
        stage('build') {
            steps {
                echo "Build branch $BRANCH_NAME"
                echo "This is second test."
            }
        }
        stage('publish') {
            steps {
                echo "Publish commit - $GIT_COMMIT for branch - $GIT_BRANCH"
            }
        }
    }
}