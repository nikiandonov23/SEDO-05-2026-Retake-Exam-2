pipeline {

    agent any

    stages {
        stage("Dotnet restore") {
            when {               //изпълнява само ако сме на main branch               
                anyOf {
                    branch 'main'
                   
                }
            }
            steps {
                bat 'dotnet restore' //Възстановявам NuGet пакетите 
            }
        }
        
        stage("Dotnet Build") { 
            when {            //Ще се изпълнява само ако съм на main branch    
                anyOf {
                    branch 'main'
                    
                }
            }
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        
        stage("Dotnet test") {
            when {  // Ще се изпълнява само ако съм на main branch               
                anyOf {
                    branch 'main'
                    
                }
            }
            steps {                
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
