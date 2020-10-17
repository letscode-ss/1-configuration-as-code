pipeline {
    agent { label 'master' }
    stages {
        stage("gradle build") { 
            steps {
                script { 
                    sh "gradle clean test"
                }
            }
        }
        stage("gradle test") { 
            steps {
                script { 
                    sh "gradle clean test"
                }
            }
        }
    }
    post {
        success {
            junit 'build/test-results/**/*.xml'
            archiveArtifacts 'build/lib/*.war'
        }
    }
}
