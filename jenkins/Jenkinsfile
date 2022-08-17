pipeline {
    agent any
    parameters {
        choice(name: 'BRANCH', choices: ['main' , 'branch1', 'master'], description: 'Select a branch')
                }
    environment {
                GIT_REPO = "https://github.com/monica261195/jenkins-qa"
                }
    stages {
        stage ("Test1") {
            steps {
                script {
                    if(params.BRANCH == 'master')
                    {
                        git branch: params.BRANCH, url: env.GIT_REPO
                        sh 'echo "This is a Test1 stage using master branch"'
                    } else { 
                        echo "Skip Test1 stage"
                        exit 1
                    }
                }
            }
        }
        stage ("Test2") {
            steps {
                script {
                    if(params.BRANCH == 'master')
                    {
                        git branch: params.BRANCH, url: env.GIT_REPO
                        echo "This is a Test2 stage using master branch" 
                    } else { 
                        echo "This is not master branch"
                        exit 1
                    }                    
                }
            }
        }
    }  
}
