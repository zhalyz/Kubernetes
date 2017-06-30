sudo systemctl daemon-reload
curl -X PUT -d "value={\"Network\":\"$POD_NETWORK\",\"Backend\":{\"Type\":\"vxlan\"}}" "$ETCD_SERVER/v2/keys/coreos.com/network/config"
sudo systemctl start flanneld
sudo systemctl enable flanneld
sudo systemctl start kubelet
sudo systemctl enable kubelet
curl http://127.0.0.1:8080/version
curl -s localhost:10255/pods | jq -r '.items[].metadata.name'
