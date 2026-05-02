pipeline {
    // Menjalankan pipeline pada agent (node) mana saja yang tersedia
    agent any

    // Mendefinisikan environment variable (opsional)
    environment {
        NODE_ENV = 'test'
    }

    stages {
        // 1. Tahap Persiapan & Instalasi Dependensi
        stage('Build / Install') {
            steps {
                echo 'Mengunduh dependensi proyek...'
                // Menjalankan perintah shell untuk install library yang ada di package.json
                sh 'npm install'
            }
        }

        // 2. Tahap Pengujian (Unit Testing)
        stage('Test') {
            steps {
                echo 'Menjalankan unit testing...'
                // Menjalankan script test yang didefinisikan di package.json
                sh 'npm test'
            }
        }

        // 3. Tahap Deploy (Simulasi)
        stage('Deploy') {
            steps {
                echo 'Aplikasi berhasil melewati tes! Memulai proses deploy...'
                // Di sini biasanya berisi perintah kirim file ke server atau push Docker image
                // Untuk tugas ini, cukup tampilkan pesan sukses
                echo 'Aplikasi berhasil dideploy ke lingkungan Staging.'
            }
        }
    }

    // Bagian post-build untuk memberikan status akhir
    post {
        always {
            echo 'Selesai menjalankan pipeline.'
        }
        success {
            echo 'Pipeline BERHASIL!'
        }
        failure {
            echo 'Pipeline GAGAL! Silakan periksa Console Output.'
        }
    }
}
