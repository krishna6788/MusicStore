pipeline {
    agent { label 'Linux'}
    stages {
        stage('Version Control System'){
            steps {
                git url:'https://github.com/krishna6788/MusicStore.git',
                    branch: 'Declarative'

            }
        }
        stage ('Build') {
            steps {
                sh 'dotnet restore ./MusicStore/MusicStore.csproj && dotnet restore ./MusicStore/MusicStore.csproj'
            }
        }
    }
}
