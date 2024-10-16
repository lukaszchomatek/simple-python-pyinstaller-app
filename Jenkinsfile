pipeline {
    agent {
        docker { image 'python:3.8' } // Obraz Dockera z Pythonem 3.8
    }
    stages {
        stage('Setup Python') {
            steps {
                sh 'sudo apt-get update'
                sh 'sudo apt-get install -y python3'
            }
        }
        stage('Build') {
            steps {
                sh 'python -m py_compile sources/add2vals.py sources/calc.py'
                stash(name: 'compiled-results', includes: 'sources/*.py*')
            }
        }
    }
}