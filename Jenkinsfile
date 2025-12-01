pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // List files
                bat 'echo Listing files... & dir'

                // Check Node and npm versions
                bat 'echo Checking Node and npm version... & node --version & npm --version'

                // Clean previous dependencies
                bat 'echo Cleaning old node_modules... & if exist node_modules rmdir /s /q node_modules'

                // Install dependencies
                bat 'echo Installing dependencies... & npm install'

                // Build project
                bat '''
                    echo Building project...
                    set PATH=%CD%\\node_modules\\.bin;%PATH%
                    npm run build
                '''
            }
        }

        stage('Verify Build Output') {
            steps {
                bat '''
                    if exist build\\index.html (
                        echo Build output OK: build\\index.html
                    ) else (
                        echo ERROR: build\\index.html not found!
                        exit 1
                    )
                '''
            }
        }

        stage('Run Tests') {
            steps {
                // Just run npm test normally
                bat 'echo Running tests... & npm test'
            }
        }
    }
}
