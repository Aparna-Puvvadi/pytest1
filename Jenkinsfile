pipeline{
    agent {label 'JDK-PY'}
    stages{
        stage ('source code') {
            steps {
                  git credentialsId: '06ed9883-6839-494a-8a24-2bff76a3cdbe', url: 'https://github.com/Aparna-Puvvadi/pytest1.git'
            }
        }
        stage ('Install dependencies') {
            steps{
                script{
                    sh 'python -m pip install'
                }
            }
        }
        stage ('Installing Packages') {
            steps{
                script{
                    sh 'pip install -r requirements.txt'
                }
            }            
        }
        stage ('Install pytest'){
            steps{
                script{
                    sh 'pip install pytest pytest-azurepipelines'
                }
            }
        }
        stage ('Install pytest cov'){
            steps{
                script{
                    sh 'pip install pytest-cov'
                }
            }
        }
        stage ('Run tests and outout results'){
            steps{
                script{
                    sh 'pytest --doctest-modules --junitxml=junit/test-results.xml --cov=. --cov-report=xml'
                }
            }
        }
    }
}   