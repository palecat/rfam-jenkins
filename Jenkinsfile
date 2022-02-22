pipeline {
    agent { dockerfile true }

    environment {
        DB_DATABASE = 'Rfam'
        DB_USER     = 'rfamro'
        DB_PORT     = '4497'
        DB_HOST     = 'mysql-rfam-public.ebi.ac.uk'
    }

    stages {
        stage('rfam-connect') {
            steps {
                sh 'mysql -u ${DB_USER} -h ${DB_HOST} -P ${DB_PORT} -D ${DB_DATABASE} < script.sql'
            }
        }
    }
}
