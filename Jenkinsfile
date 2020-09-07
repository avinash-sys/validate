properties(
        [
                buildDiscarder(
                        logRotator(artifactDaysToKeepStr: '',
                                artifactNumToKeepStr: '',
                                daysToKeepStr: '10',
                                numToKeepStr: '10'
                        )
                ),
                //disableConcurrentBuilds(),
                durabilityHint('MAX_SURVIVABILITY'),
                disableResume(),
                [
                        $class      : 'CopyArtifactPermissionProperty',
                        projectNames: '*'
                ],
                parameters(
                        [
                                booleanParam(
                                        defaultValue: true,
                                        description: 'Do u want to use mounted maven?',
                                        name: 'MOUNT_MAVEN'
                                ),
                                string(
                                        defaultValue: 'master',
                                        description: 'To build a branch',
                                        name: 'BUILD_BRANCH',
                                        trim: true
                                ),
                                string(
                                        defaultValue: 'N/A',
                                        description: 'To build a tag',
                                        name: 'USER_BUILD_TAG',
                                        trim: true
                                ),
                                booleanParam(
                                        defaultValue: false,
                                        description: 'Is this triggered from upstream?',
                                        name: 'UPSTREAM_TRIGGERED'
                                )
                        ]
                )
        ])

pipeline {
    agent any
    stages {
        stage('build the code') {
            steps {
                echo "Validation is Successful"
		        build job: 'integrate',
                        parameters: [
                                booleanParam(name: 'MOUNT_MAVEN', value: true),
                                string(name: 'BUILD_BRANCH', value: 'master'),
                                string(name: 'USER_BUILD_TAG', value: 'N/A'),
                        ]
            }
        }
    }
}
