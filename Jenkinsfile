pipeline {
    agent any
    
    environment {
        VERCEL_PROJECT_ID = 'devops18-quiz1'
        VERCEL_TOKEN = credentials('DevOps18-quiz1') 
    }

    stages {
        stage('Test npm') {
            steps {
                echo 'Installing and Testing...'
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Project...'
                sh 'npm run build'
            }
        }

        stage('Test Build') {
            steps {
                echo 'Checking Build Output...'
                sh 'ls -al' 
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying to Vercel...'
                sh "npx vercel --token ${VERCEL_TOKEN} --prod --yes"
            }
        }
    }
}