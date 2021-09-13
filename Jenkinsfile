pipeline {
    agent {
        label 'master'
    }
    
    parameters {
        booleanParam(name: 'unit_validate', defaultValue: true, description: 'amd64 (x86_64) unit tests and vendor check')
        booleanParam(name: 'validate_force', defaultValue: false, description: 'force validation steps to be run, even if no changes were detected')
        booleanParam(name: 'amd64', defaultValue: true, description: 'amd64 (x86_64) Build/Test')
        booleanParam(name: 'rootless', defaultValue: true, description: 'amd64 (x86_64) Build/Test (Rootless mode)')
        booleanParam(name: 'cgroup2', defaultValue: true, description: 'amd64 (x86_64) Build/Test (cgroup v2)')
        booleanParam(name: 'arm64', defaultValue: true, description: 'ARM (arm64) Build/Test')
        booleanParam(name: 's390x', defaultValue: false, description: 'IBM Z (s390x) Build/Test')
        booleanParam(name: 'ppc64le', defaultValue: false, description: 'PowerPC (ppc64le) Build/Test')
        booleanParam(name: 'windowsRS1', defaultValue: false, description: 'Windows 2016 (RS1) Build/Test')
        booleanParam(name: 'windowsRS5', defaultValue: true, description: 'Windows 2019 (RS5) Build/Test')
        booleanParam(name: 'windows2022', defaultValue: true, description: 'Windows 2022 (LTSC) Build/Test')
        booleanParam(name: 'windows2022containerd', defaultValue: true, description: 'Windows 2022 (LTSC) with containerd Build/Test')
        booleanParam(name: 'dco', defaultValue: true, description: 'Run the DCO check')
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
                echo "Not Build branch $GIT_BRANCH"
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
