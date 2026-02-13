pipeline {
    agent any 
    
    stages {
        
        stage ('git checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/sharmaaman52/webapp.git'
             }
        }
        
        stage ('Build the application') {
            steps {
                sh '''
                ansible-playbook -i inventory.ini /var/lib/jenkins/workspace/ansible-project/playbook.yml --limit dev
                '''
            }
        }
        
        stage ('Test application') {
            steps {
                sh '''
                curl -f http://172.31.32.226
                '''
            }
        }
    }
}
