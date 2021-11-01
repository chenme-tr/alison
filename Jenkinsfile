pipeline {
    agent any
    parameters {
        string(name: 'DockerFile', defaultValue: 'Dockerfiletemp', description: 'blablabla')
    }
    stages {
        stage('Build') {
            steps {
                sh """ pip3 install . 
                    python3 tests.py """
            }
        }
        stage('Test') {
            steps {
                sh """
                    sudo docker build -t alison . -f ${params.DockerFile} 
                    echo ${params.DockerFile}
                """
            }
        }
        stage('Artifact'){
            steps {
                echo 'Push the artifact to Jfrog Artifactory'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
