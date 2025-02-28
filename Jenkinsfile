pipeline {
    agent any

    stages {
        stage('Clonar repositorio') {
            steps {
                git branch: 'main', url: '<URL_DEL_REPOSITORIO>'
            }
        }

        stage('Instalar dependencias') {
            steps {
                sh 'npm install'
            }
        }

        stage('Ejecutar pruebas') {
            steps {
                sh 'npm test' // Asegúrate de tener pruebas configuradas
            }
        }

        stage('Construir imagen Docker') {
            steps {
                sh 'docker build -t my-app .'
            }
        }

        stage('Desplegar') {
            steps {
                sh 'docker run -d -p 3000:3000 my-app'
            }
        }
    }
}
