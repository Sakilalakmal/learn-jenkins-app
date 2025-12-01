pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                bat '''
                    echo Listing files...
                    dir

                    echo Checking Node and npm version...
                    node --version
                    npm --version

                    echo Installing dependencies...
                    npm ci

                    echo Building project...
                    npm run build
                '''
            }
        }
    }
}
