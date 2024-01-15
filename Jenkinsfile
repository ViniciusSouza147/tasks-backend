pipeline{
    agent any
    stages{
        stage ("Build Backend"){
            steps{
                echo "======== Executing Test ========"
                sh 'mvn clean package -DskipTests=true'
            }
        }
        stage ("Unit Test"){
            steps{
                echo "====++++ Executing Unit Test ++++===="
                sh 'mvn test'
            }
        }
        stage ("Sonar Analysis"){
            environment (
                scannerHome = tool 'SONAR_SCANNER'
            )
            steps{
                script {
                    def scannerHome = tool 'SONAR_SCANNER'
                    echo "====++++ Executing Sonar Analysis ++++===="
                    withSonarQubeEnv('SONAR_LOCAL') {
                        sh "${scannerHome}/bin/sonar-scanner -e -Dsonar.projectKey=DeployBack -Dsonar.host.url=http://127.0.0.1:9000 -Dsonar.login=88e44ed433a6bb3b41dc97da1dc6fe71685d7025 -Dsonar.java.binaries=target"
                    }
                }
            }
        }
    }
}

