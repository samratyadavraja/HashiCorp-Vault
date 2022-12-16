
pipeline {
    agent any
    
    stages {
        stage('vault creation') {
            steps {
                //withCredentials([aws(accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'DevopsAdminAccount', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY')]) {
                //withCredentials([kubeconfigFile(credentialsId: 'kube-config', variable: 'KUBECONFIG')]) {
                 //sh '''echo "$KUBECONFIG" > kubeconfig && cat kubeconfig && kubectl get nodes'''
                 sh """ 
                 wget https://releases.hashicorp.com/vault/1.0.3/vault_1.0.3_linux_amd64.zip
                 unzip vault_1.0.3_linux_amd64.zip -d .
                 sudo cp vault /usr/bin/
                 sudo mkdir /etc/vault
                 sudo mkdir /opt/vault-data
                 sudo mkdir -p /logs/vault/
                 sudo vi /etc/vault/config.json
                 sudo vi /etc/systemd/system/vault.service
                 sudo systemctl start vault.service
                 sudo systemctl status vault.service
                 """
               }
            }
        }
     }     
   }
}
