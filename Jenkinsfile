pipeline{
    agent any
    stage('source code'){
        steps{
              
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
    stage('publish test results'){
        steps{
            script{
                   junit '**/test-*.xml'                
            }
        }
    }
}