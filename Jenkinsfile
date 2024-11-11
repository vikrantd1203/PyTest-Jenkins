pipeline {
    agent any
    stages {
        stage('setup') {
            steps {
                browserstack(credentialsId: '') {
                    // Set up Python environment, activate it, install dependencies, and run tests in one step
                    sh '''
                        python3 -m venv env          # Creates a virtual environment
                        source env/bin/activate      # Activates the virtual environment on Mac/Linux
                        pip3 install -r requirements.txt  # Installs dependencies
                        browserstack-sdk pytest -s tests/bstack-sample-test.py  # Runs the tests
                    '''
                }
            }
        }
    }
}
