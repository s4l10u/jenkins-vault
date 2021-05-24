def secrets = [
  [path: 'secret/github', engineVersion: 2, secretValues: [
    [envVar: 'DB_NAME', vaultKey: 'name'],
    [envVar: 'URL', vaultKey: 'url'],
    [envVar: 'USERNAME', vaultKey: 'username'],
    [envVar: 'PASSWORD', vaultKey: 'password']]],
]
def configuration = [vaultUrl: 'https://vault.eva.sn',  vaultCredentialId: 'vault-approle', engineVersion: 2]
                      
pipeline {
    agent any
    stages{   
      stage('Vault') {
        steps {
          withVault([configuration: configuration, vaultSecrets: secrets]) {
            sh "echo ${env.DB_NAME}"
            sh "echo ${env.URL}"
            sh "echo ${env.USERNAME}"
            sh "echo ${env.PASSWORD}"
          }
        }  
      }
    }
}

