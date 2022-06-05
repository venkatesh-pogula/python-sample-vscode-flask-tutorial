pipeline{
    agent{ label 'node_java_11'}
    stages{
        stage('scm'){
            steps{
                git branch: 'master' , url: 'https://github.com/venkatesh-pogula/python-sample-vscode-flask-tutorial.git'
            }
        }
        stage('build'){
            steps{
                sh "pip install -r requirements.txt"
            }
        }
        stage('pytest'){
            steps{
                sh "pytest"
            }
        }
        stage('flake'){
            steps{
                sh "flake8 ."
            }
        }
    }
    post{
        success{
            junit '**/test-*.xml'
        }
    }
}