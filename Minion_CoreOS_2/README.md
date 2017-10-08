/etc/flannel/options.env
<br>/etc/systemd/system/flanneld.service.d/40-ExecStartPre-symlink.conf
<br>/etc/systemd/system/docker.service.d/40-flannel.conf
<br>/etc/systemd/system/kubelet.service
<br>/etc/kubernetes/manifests/kube-proxy.yaml
<br>/etc/kubernetes/worker-kubeconfig.yaml
<br>sudo systemctl daemon-reload
<br>sudo systemctl start kubelet
<br>sudo systemctl enable kubelet
<br>systemctl status kubelet.service

