pipeline {
    agent any

    stages {
        stage('initws') {
            steps {
                //Clean workspace before init
                echo 'cleanWs'
                cleanWs()
            }
        }
    
    
        stage('gitinit') {
            steps {
                echo 'gitinit'
                git branch: 'main', url: 'https://github.com/Elad0109/simple-webapp-nodejs-'
            }
        }
        stage('build') {
            steps {
                echo 'build'
                nodejs('nodejs') {
                    // run build
                    sh "npm install"
                }
            }
        }
        stage('test') {
            steps {
                echo 'test'
                nodejs('nodejs') {
                    // run test
                    sh "npm run test"
                }
            }
        }
        stage('deploy') {
            steps {
                echo 'deploy'
                nodejs('nodejs') {
                    // run deploy
                    sh "npm run start"
                }
            }
        }
    
    }
}
