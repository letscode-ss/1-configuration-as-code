pipeline {
    agent { label 'master' }
    stages {
        stage("gradle test") { 
            steps {
                script { 
                    sh "gradle clean test"
                }
            }
        }
        stage("gradle assemble") { 
            steps {
                script { 
                    sh "gradle assemble"
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
