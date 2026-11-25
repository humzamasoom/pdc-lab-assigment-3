pipeline {
    agent any

    triggers {
        githubPush()
    }

    options {
        disableConcurrentBuilds()
        buildDiscarder(logRotator(numToKeepStr: '10'))
        timeout(time: 5, unit: 'MINUTES')
    }

    stages {
        stage('Compile') {
            steps {
                sh 'mkdir -p build && javac -d build HelloWorld.java'
            }
        }
        stage('Run') {
            steps {
                sh 'java -cp build HelloWorld'
            }
        }
    }
}
