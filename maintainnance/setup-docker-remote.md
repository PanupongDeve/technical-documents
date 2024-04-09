
1. sudo su  
2. vim /lib/systemd/system/docker.service  
3. replace -> ExecStart=/usr/bin/dockerd -H fd:// -H tcp://0.0.0.0:2375 --containerd=/run/containerd/containerd.sock  
4. systemctl daemon-reload  
5. systemctl restart docker.service
6. sudo netstat -lntp | grep dockerd  