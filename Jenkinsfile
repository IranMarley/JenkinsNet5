pipeline {
 agent any
 environment {
  dotnet = 'C:\Program Files\dotnet\dotnet.exe'
 }
 stages {
   stage('Checkout') {
    steps {
     git credentialsId: 'cc8158f2-fbcb-4e10-90d7-5002d4207a9e', url: 'https://github.com/IranMarley/JenkinsNet5.git/', branch: 'master'
     }
  }
stage('Restore packages'){
   steps {
		bat "dotnet restore D:\\Projetos\\JenkinsNet5\\JenkinsNet5\\JenkinsNet5.csproj"
   }
  }
  stage('Clean') {
   steps {
        bat "dotnet clean D:\\Projetos\\JenkinsNet5\\JenkinsNet5\\JenkinsNet5.csproj"
   }
  }
  stage('Build') {
   steps {
		bat "dotnet build D:\\Projetos\\JenkinsNet5\\JenkinsNet5\\JenkinsNet5.csproj --configuration Release"
   }
  }
  stage('Publish') {
   steps {
		bat "dotnet publish D:\\Projetos\\JenkinsNet5\\JenkinsNet5\\JenkinsNet5.csproj -o D:\\IIS\\JenkinsNet5"
   }
  }
 }
}


