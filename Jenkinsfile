pipeline{
    agent any
    stages{
        stage("Build Backend"){
            steps{
                echo "======== Executing Teste ========"
                sh 'mvn clean package -DskipTests=true'
            }
        }
    }
}