pipeline {
    agent any
    environment {
        SECRET = vault path: 'secret/github', key: 'username', vaultUrl: 'https://vault.eva.sn', credentialsId: 'vault-approle', engineVersion: "2"
    }
    stages {
        stage("read  vault key Test") {
            steps {
                echo "${SECRET}"
            }
        }
    }
}

