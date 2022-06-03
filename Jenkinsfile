pipeline{
    agent any
    stage('source code'){
        steps{
            git branch: 'master', url: 'https://github.com/Aparna-Puvvadi/pytest1.git'
        }
    }
    stage('Install dependencies'){
        steps{
            script{
                sh 'python -m pip install'
            }
        }
    }
    stage('Installing Packages'){
        steps{
            script{
                sh 'pip install -r requirements.txt'
            }
        }
    }
    stage('Run test'){
        steps{
            script{
                  sh 'pip install tox'
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