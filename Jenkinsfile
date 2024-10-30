pipeline {
    agent any
    stages {
        stage('setup') {
            steps {
                browserstack(credentialsId: '456789') {
                    // Set up Python environment and install dependencies
                    sh 'python3 -m venv env' // Creates a virtual environment
                    sh 'source env/bin/activate' // Activates the virtual environment on Mac/Linux
                    // Install dependencies and run tests
                    sh 'pip install -r requirements.txt'
                    sh 'browserstack-sdk pytest -s tests/bstack-sample-test.py'
                }
            }
        }
    }
}
