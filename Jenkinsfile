pipeline {
    agent {
        label 'master'
    }
    stages {
        stage('pr-hack') {
            when { changeRequest() }
            steps {
                script {
                    echo "Workaround for PR auto-cancel feature. Borrowed from https://issues.jenkins-ci.org/browse/JENKINS-43353"
                    def buildNumber = env.BUILD_NUMBER as int
                    if (buildNumber > 1) milestone(buildNumber - 1)
                    milestone(buildNumber)
                }
            }
        }
        
        stage('build') {
            steps {
                echo "Build branch $GIT_BRANCH"
                echo "This is first test"
            }
        }
        stage('publish') {
            steps {
                echo "Publish commit - $GIT_COMMIT for branch - $GIT_BRANCH"
                echo "This is a 2nd test for pipeline"
                echo "finished"
            }
        }
    }
}
