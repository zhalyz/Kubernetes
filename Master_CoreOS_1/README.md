sudo systemctl daemon-reload
<br>curl -X PUT -d "value={\"Network\":\"$POD_NETWORK\",\"Backend\":{\"Type\":\"vxlan\"}}" "$ETCD_SERVER/v2/keys/coreos.com/network/config"
<br>sudo systemctl start flanneld
<br>sudo systemctl enable flanneld
<br>sudo systemctl start kubelet
<br>sudo systemctl enable kubelet
<br>curl http://127.0.0.1:8080/version
<br>curl -s localhost:10255/pods | jq -r '.items[].metadata.name'
<br>
<br>
<br>
<br>curl -O https://storage.googleapis.com/kubernetes-release/release/v1.6.1/bin/linux/amd64/kubectl
<br>chmod +x kubectl
<br>mv kubectl /usr/local/bin/kubectl
<br>kubectl config set-cluster default-cluster --server=https://${MASTER_HOST} --certificate-authority=${CA_CERT}
<br>kubectl config set-credentials default-admin --certificate-authority=${CA_CERT} --client-key=${ADMIN_KEY} --client-<br>certificate=${ADMIN_CERT}
<br>kubectl config set-context default-system --cluster=default-cluster --user=default-admin
<br>kubectl config use-context default-system
<br>kubectl get nodes
