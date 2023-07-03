# CKA
note during the cka preparation


```
- manully scheduling: node name
- k get all 
- effect not effet for tolerations
- https://kubernetes.io/docs/concepts/scheduling-eviction/assign-pod-node/#operators
- kubectl run static-busybox --image=busybox --dry-run=client -oyaml --command -- sleep 1000 > static-busybox.yaml
- static pod need to be deleted to apply the change
- kubelet config: /var/lib/kubelet/config.yaml -> has the staticPath setting
- kubectl set-content
- Dockerfile’s entrypoint can be overwrite by the pod command. And you can also use args to add the options for the command
- etcd snapshot need endpoint cert ca and key (and snapshot api on v3)
- restore etcd db need to be chown -R etcd:etcd <dir>
- etcd service config file: /etc/systemd/system/etcd.service
- etcd-server /etc/systemd/system ➜  vi etcd.service 
- etcd-server /etc/systemd/system ➜  systemctl daemon-reload
- etcd-server /etc/systemd/system ➜  systemctl restart etcd
- registry has to be host/imagename:tag
- network interface: ip address | grep {node_ip} filter: ip addr show eth0 get brige: ip addr show type brige
- ping a host : ip route (default)
- which port the pod is listenning:  netstat -lnp | grep -i scheduler
- cal connexion: netstat -anp | grep etcd | grep {port} | wc -l
- netshot image: nicolaka/netshot
- journalctl -u kubelet to get logs of kubelet
- Test pod dns
	Get the IP of the nginx-resolver pod and replace the dots(.) with hyphon(-) which will be used 	below.
	kubectl get pod nginx-resolver -o wide
	kubectl run test-nslookup --image=busybox:1.28 --rm -it --restart=Never -- nslookup <P-O-D-	I-P.default.pod> > /root/CKA/nginx.pod
```
