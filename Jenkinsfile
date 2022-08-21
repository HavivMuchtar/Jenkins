pipeline {
    agent any

    stages {
        stage('initws') {
            steps {
                // Clean workspace before init
                cleanWs()
                echo 'clean workspace'
            }
        }
        stage('gitinit') {
            steps {
                echo 'git init'
                git branch: 'main', url: 'https://github.com/Elad0109/simple-webapp-nodejs-.git'
            }
        }
        stage('build') {
            steps {
                echo 'build'
                nodejs('nodejs 18.7.0') {
                    // some block
                    // npm build
                    sh "npm install"
                }
            }
        }
        stage('test') {
            steps {
                echo 'test'
                nodejs('nodejs 18.7.0') {
                    // some block
                    // npm run
                    sh "npm run test"
                }
            }
        }
        stage('depoly') {
            steps {
                echo 'depoly'
                nodejs('nodejs 18.7.0') {
                    // some block
                    // npm start
                    sh "npm run start"
                }
            }
        }
    }
}
