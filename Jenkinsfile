pipeline {
    agent any
    parameters {
        string(name: 'Dockerfile', defaultValue: 'Dockerfiletemp', description: 'Dockerfile name to build')
    }
    stages {
        stage('Test') {
            steps {
                sh ''' echo \'installing libs\'
                pip3 install .
                echo \'running tests\'
                python3 tests.py '''
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}