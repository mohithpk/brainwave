pipeline {
    agent { label "project1" }

    stages {
        stage('1st stage- git clone') {
            steps {
                git branch: 'main', url: 'https://github.com/mohithpk/brainwave.git'
            }
        }
        stage('2nd stage- docker build') {
            steps {
                sh 'docker build -t brainwave-mohith1.0 .'
            }
        }
        stage('3rd stage- docker tag') {
            steps {
                sh 'docker tag brainwave-mohith1.0 mohithp/brainwave-mohith1.0'
            }
        }
        stage('4th stage- docker run') {
            steps {
               sh 'docker stop brainwave-mohith1.0 || true'
               sh 'docker rm brainwave-mohith1.0 || true'
               sh 'docker run -d --name brainwave-mohith1.0 -p 84:80 mohithp/brainwave-mohith1.0'
            }
        }
        stage('5th stage- docker login') {
            steps {
               sh 'docker login -u mohithp -p Tvisha123@'
            }
        }
        stage('6th stage- docker push') {
            steps {
               sh 'docker push mohithp/brainwave-mohith1.0'
            }
        }
    }
}
