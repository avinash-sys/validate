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
                                        defaultValue: 'N/A',
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
                                        description: 'Need debug information from Maven',
                                        name: 'MVN_DEBUG'
                                ),
                                booleanParam(
                                        defaultValue: false,
                                        description: 'Is this triggered from upstream?',
                                        name: 'UPSTREAM_TRIGGERED'
                                ),
								booleanParam(
                                        defaultValue: false,
                                        description: 'Marking builds forever for master and tagged builds',
                                        name: 'BUILD_FOREVER'
                                ),
                                string(
                                        defaultValue: 'N/A',
                                        description: 'To build a tag',
                                        name: 'UPSTREAM_BUILD_NUMBER',
                                        trim: true
                                ),
                                string(
                                        defaultValue: 'N/A',
                                        description: 'Designer Docker Image Build Number to use',
                                        name: 'DESIGNER_DOCKER_IMAGE_NO',
                                        trim: true
                                ),
                                string(
                                        defaultValue: 'N/A',
                                        description: 'Build Utils Build Number to use',
                                        name: 'BUILD_UTILS_BUILD_NO',
                                        trim: true
                                ),
                                string(
                                        defaultValue: 'N/A',
                                        description: 'Test Utils Build Number to use',
                                        name: 'TEST_UTILS_BUILD_NO',
                                        trim: true
                                ),
                                string(
                                        defaultValue: 'N/A',
                                        description: 'Volante path to fetch',
                                        name: 'VOLANTE_PATH',
                                        trim: true
                                )
                        ]
                )
        ])


pipeline {
    agent any
    stages {
        stage('validate the code') {
            steps {
                echo "code validate is successfull"
            }
        }
    }
}
