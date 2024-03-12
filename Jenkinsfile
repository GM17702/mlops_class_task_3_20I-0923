pipeline {
    agent any
    
    stages {

        stage('Cloning from git') {
            steps {
                git branch: 'main', url: 'https://github.com/GM17702/mlops_class_task_3_20I-0923'
            }
        }

        stage('Set up Python') {
            steps {
                script {
                    // No setup required for Python on Windows, it's pre-installed
                }
            }
        }

        stage('Installation of dependencies') {
            steps {
                bat 'pip install -r requirement.txt'
                echo 'Dependencies successfully installed!'
            }
        }

        stage('Test') {
            steps {
                bat 'python test.py'
                echo 'Tests passed!'
            }
        }

        stage('Deploy') {
            steps {
                script {
                    if (env.BRANCH_NAME == 'main') {
                        echo 'Deploying to production...'
                        
                    } else {
                        echo 'Deploying to development server...'
                        
                    }
                }
            }
        }
    }
}
