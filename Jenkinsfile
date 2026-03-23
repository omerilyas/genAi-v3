pipeline {
    agent {
        docker {
            image 'danischm/cl-labs:0.1.1'
            label 'emear-sio-slv05'
            args '-u root'
        }
    }

    environment { 
        GITHUB_TOKEN = credentials('GITHUB_TOKEN')
    }

    stages {
        stage('Publish Documentation') {
            when {
                branch 'master'
            }
            steps {
                sh 'git config --global --add safe.directory "*"'
                sh 'git config credential.helper "store --file=.git/credentials"'
                sh 'echo "https://$GITHUB_TOKEN:@wwwin-github.cisco.com" > .git/credentials'
                sh 'mkdocs gh-deploy --force'
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}