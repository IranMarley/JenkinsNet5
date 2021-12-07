pipeline {
 agent any
 environment {
  dotnet = 'C:\\Program Files\\dotnet\\dotnet.exe'
 }
 stages {
   stage('Checkout') {
    steps {
     git credentialsId: 'b11b3c89-c700-4aff-9411-bf559861dffc', url: 'https://github.com/IranMarley/JenkinsNet5.git/', branch: 'master'
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
		bat "net stop was /y"
		bat "dotnet publish D:\\Projetos\\JenkinsNet5\\JenkinsNet5\\JenkinsNet5.csproj -o D:\\IIS\\JenkinsNet5"
		bat "net start w3svc"
   }
  }
 }
}


