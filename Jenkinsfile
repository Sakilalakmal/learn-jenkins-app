pipeline {
    agent any

    stages {
        stage('Install & Build') {
            steps {
                bat '''
                    echo Listing project files...
                    dir

                    echo Checking Node & NPM version...
                    node --version
                    npm --version

                    echo Installing dependencies...
                    npm install

                    echo Building project...
                    npm run build
                '''
            }
        }
    }
}
