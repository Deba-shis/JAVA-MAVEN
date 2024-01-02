Project using jenkins+docker+kubernetes using pipeline script

1.copy the code
2.build the project
==============================================================================================================
3.create the image
install docker in jenkins machine
 1.curl -fsSL get.docker.com | /bin/bash 
 2. Add Jenkins user to docker group 
 sudo usermod -aG docker jenkins 
 3. Restart Jenkins 
 sudo systemctl restart jenkins
===============================================================================================================
4.install kubectl in jenkins server accessing the pods and nodes
$ curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl" 
$ chmod +x ./kubectl 
$ sudo mv ./kubectl /usr/local/bin/kubectl 
$ kubectl version 
$ mkdir ~/.kube 
Note: Take kube config file from master node using below command and copy that 
$ cat ~/.kube/config 
# Paste Master Node Kube config file data here 
$ vi ~/.kube/config 
$ kubectl cluster-info 
$ kubectl get node
===============================================================================================================
Connection kubernetes with jenkins
https://www.youtube.com/watch?v=rc7jZrA2aKk
https://www.fosstechnix.com/integrate-remote-kubernetes-cluster-with-jenkins/