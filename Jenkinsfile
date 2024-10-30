pipeline {
    agent any
    stages {
        stage('setup') {
            steps {
                browserstack(credentialsId: '833c8871-ab95-4280-9199-9c2469b191d9') {
                    // Set up Python environment and install dependencies
                    sh 'python3 -m venv env' // Creates a virtual environment
                    sh 'source env/bin/activate' // Activates the virtual environment on Mac/Linux
                    // Install dependencies and run tests
                    sh 'pip3 install -r requirements.txt'
                    sh 'pip3 install browserstack-sdk==1.22.5'
                    sh 'browserstack-sdk pytest -s tests/bstack-sample-test.py'
                }
            }
        }
    }
}
