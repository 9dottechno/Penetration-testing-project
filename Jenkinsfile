# Jenkins Pipeline for AI-Powered Pentest
pipeline {
    agent any
    stages {
        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
                sh 'pip install selenium python-docx reportlab hvac boto3 azure-identity azure-keyvault-secrets'
            }
        }
        stage('Run Pentest Framework') {
            steps {
                sh 'python pentest_framework.py'
            }
        }
        stage('Archive Reports') {
            steps {
                archiveArtifacts artifacts: 'pentest_report.json,pentest_report.pdf,pentest_report.docx,dashboard_data.json,attestation_certificate.json', allowEmptyArchive: true
            }
        }
    }
}
