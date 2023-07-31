pipeline {
    agent { label 'Linux'}
    stages {
        stage('Version Control System'){
            steps {
                git url:'https://github.com/krishna6788/nopCommerce.git',
                    branch: 'Declarative'

            }
        }
        stage ('Build') {
            steps {
                sh 'dotnet restore src/NopCommerce.sln'
                sh 'dotnet build src/NopCommerce.sln'

            }
        }
        
    }
}