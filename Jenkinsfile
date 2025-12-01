pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                bat '''
                    echo Listing files...
                    dir

                    echo Checking Node & npm version...
                    node --version
                    npm --version

                    echo Installing dependencies...
                    npm install

                    echo Building...
                    npm run build

                    echo Done!
                '''
            }
        }
    }
}
