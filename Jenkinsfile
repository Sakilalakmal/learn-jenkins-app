pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                // List files
                bat 'echo Listing files... & dir'

                // Check Node and npm versions
                bat 'echo Checking Node and npm version... & node --version & npm --version'

                // Clean previous dependencies (optional, ensures clean install)
                bat 'echo Cleaning old node_modules... & if exist node_modules rmdir /s /q node_modules'

                // Install dependencies
                bat 'echo Installing dependencies... & npm install'

                // Build project (ensures PATH includes node_modules/.bin)
                bat '''
                    echo Building project...
                    set PATH=%CD%\\node_modules\\.bin;%PATH%
                    npm run build
                '''
            }
        }
    }
}
