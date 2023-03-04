pipeline {
    agent { label 'dotnet6' }
    triggers { pollSCM('* * * * *') }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/khajadevopsmarch23/MusicStore.git'
            }
        }
        stage('build') {
            steps {
                sh 'dotnet restore ./MusicStore/MusicStore.csproj && dotnet build ./MusicStore/MusicStore.csproj'
            }
        }
        stage('test') {
            steps {
                sh 'dotnet test --logger "junit;LogFilePath=TEST-musicstoretest.xml" ./MusicStoreTest/MusicStoreTest.csproj'
                junit testResults: '**/TEST-*.xml'
            }
        }
    }
}