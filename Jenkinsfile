pipeline {
    agent {label 'OPENJDK-11'}
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('pull from vcs') {
         steps {
            git url: 'https://github.com/Qtalha/shopizer.git',
            branch: 'develop' 
           }
        
        }
        stage("build") {
            steps {
                sh 'mvn package'
            }
        }
    }
}
