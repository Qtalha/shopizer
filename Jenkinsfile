pipeline {
    agent {label 'OPENJDK-11'}
    triggers {
        pollSCM ('30 17 * * *')
    }
    stages {
        stage('pull from vcs') {
         steps {
            git url: 'https://github.com/Qtalha/shopizer.git',
            branch: 'master' 
           }
        }
        stage('run') {
            steps {
                sh 'git config --global user.email "quazitalhazuhair84@gamail.com"'
                sh 'git config --global user.name "Qtalha"'
            }
        }
        stage("merge") {
            steps {
                sh 'git checkout master'
                sh 'git merge --no-ff origin/conflict'
            }
        }
        stage("build") {
            steps {
                sh 'mvn package'
            }
        }
    }
}

