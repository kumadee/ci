pipeline {
    agent {
        label 'master'
    }
    stages {
        stage('build') {
            steps {
                echo "Build branch $BRANCH_NAME"
                echo "This is first test"
            }
        }
        stage('publish') {
            steps {
                echo "Publish commit - $GIT_COMMIT for branch - $GIT_BRANCH"
                echo "This is a 2nd test for pipeline"
            }
        }
    }
}
