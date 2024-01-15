pipeline{
    agent any
    stages{
        stage("Build Backend"){
            steps{
                echo "======== Executing Test ========"
                sh 'mvn clean package -DskipTests=true'
            }
        }
        stage("Unit Test"){
            steps{
                echo "====++++ Executing Unit Test ++++===="
                sh 'mvn test'
            }
        }
    }
}