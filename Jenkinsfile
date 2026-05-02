pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Sedang mengunduh library (npm install)...'
                // Menggunakan 'bat' karena kamu menggunakan Windows
                bat 'npm install'
            }
        }

        stage('Test') {
            steps {
                echo 'Sedang menjalankan unit testing...'
                bat 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Project berhasil di-build dan di-test!'
                echo 'Simulasi: Deploy ke server berhasil.'
            }
        }
    }

    post {
        success {
            echo 'Selamat! Pipeline berhasil berjalan sempurna.'
        }
        failure {
            echo 'Waduh! Ada yang error. Cek kembali Console Output-nya.'
        }
    }
}
