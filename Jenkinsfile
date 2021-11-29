pipeline {
    agent any
    stages {
        stage('Checkout') {
            // checkout([
            //     $class: 'GitSCM',
            //     branches: scm.branches,
            //     extensions: scm.extensions + [[$class: 'LocalBranch'], [$class: 'WipeWorkspace']],
            //     userRemoteConfigs: [[credentialsId: 'Bitbucket', url: 'git@bitbucket.org:NAVFREG/jenkinsfile-tests.git']],
            //     doGenerateSubmoduleConfigurations: false
            // ])
        }

        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        post {
           always {
               jiraSendBuildInfo site: 'saradarbank.atlassian.net'
               // jiraSendBuildInfo branch: 'builds', site: 'saradarbank.atlassian.net'
           }
       }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}