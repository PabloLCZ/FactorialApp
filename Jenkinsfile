pipeline {
    agent any

    tools {
        maven 'Maven 3.9.9'      // Asegúrate de que este nombre esté bien en Jenkins > Global Tool Configuration
        jdk 'Java 17'            // Cambia a 'Java 17' si ese es el nombre del JDK que configuraste
    }

    stages {
        stage('Clonar') {
            steps {
                git 'https://github.com/PabloLCZ/FactorialApp.git' // Sustituye tu-usuario por tu nombre de GitHub
            }
        }

        stage('Compilar') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Pruebas') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Empaquetar') {
            steps {
                sh 'mvn package'
            }
        }
    }

    post {
        success {
            echo '✅ Build y pruebas exitosas'
        }
        failure {
            echo '❌ Falló el proceso'
        }
    }
}
