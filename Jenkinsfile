pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/master']],
                    userRemoteConfigs: [[
                        url: 'https://github.com/piona/ant-sample.git'
                    ]]
                ])
            }
        }

        stage('Build with Ant') {
            steps {
                // sh "ant clean"
                // sh "ant compile"
                sh "ant build"   // or your custom target
            }
        }

        // stage('Archive Artifacts') {
        //     steps {
        //         archiveArtifacts artifacts: 'build/**/*.jar', fingerprint: true
        //     }
        // }

    }
}
