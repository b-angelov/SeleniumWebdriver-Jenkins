pipeline{
    agent any

    environment{
        CHROME_VERSION =  '137.0.7151.104';
        CHROMEDRIVER_VERSION = "137.0.7151.7000";
        CHROME_INSTALL_PATH = 'C:\\Program Files\\Google\\Chrome\\Application'
        CHROMEDRIVER_PATH = 'C:\\Program Files\\Google\\Chrome\\Application\\chromedriver-win64\\chromedriver.exe'
    }

    stages{
        stage("Checkout code"){
            steps{
                git branch: 'main', url: 'https://github.com/b-angelov/SeleniumWebdriver-Jenkins.git';
            }
        }

        stage("Setup .NET"){
            steps{
                bat "choco install dotnet-sdk -y --version=6.0.100"
            }
        }

        stage("Restore dependencies"){
            steps{
                bat "dotnet restore SeleniumBasicExercise.sln"
            }
        }

        stage("Build"){
            steps{
                bat "dotnet build SeleniumBasicExercise.sln"
            }
        }
        
        stage("Test project 1"){
            steps{
                bat "dotnet test TestProject1"
            }
        }

        stage("Test project 2"){
            steps{
                bat "dotnet test TestProject2"
            }
        }

        stage("Test project 3"){
            steps{
                bat "dotnet test TestProject3"
            }
        }

    }
}