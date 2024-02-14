# Maven 

* -- JDK & Maven Installation --

 ``sudo apt-get update -y``
  ``sudo apt install openjdk-11-jre -y``
    ``sudo apt-get install maven -y``

* version check 
` java -version `
` mvn -version `

*Build Project:
### first of clone repository and go inside the project

* command validate project ignored the all warning

` mvn validate ` 

* check syntax base error and All Dependency Download
` mvn compile `

* go inside target folder for output 3 folder (classes, generated-sources, maven-status) cd ..
* next command Test inside project folder
` mvn test `

` mvn package `

8 go target foldar check .jar file and back project folder

` mvn install `

* clean package

` mvn clean package `

* java base project temporary execute jar file for default port:8080

` java -jar target/spring-boot-web.jar `
 




















# Master_academy 
## DevOps-Error solving
* Kubernetes master Node problem errors solution:

*Kubernetes Error Master Node in Ubuntu Server Version Vm*

> error execution phase wait-control-plane: couldn't initialize a Kubernetes 
> cluster To see the stack trace of this error execute with --v=5 or higher.

* Error Solve In follow Step By Step command:
 
  ``kubeadm reset -f``
 
 >``iptables -F && iptables -t nat -F && iptables -t mangle -F && iptables -X``
 
 >``cat > /etc/docker/daemon.json <<EOF``
 
 * Select all Command:
``` 
{
  "exec-opts": ["native.cgroupdriver=systemd"],
  
  "log-driver": "json-file",
  
  "log-opts": {
  
   "max-size": "100m"
	
  },
  
  "storage-driver": "overlay2"
  
 }
EOF 
```
 

>`systemctl daemon-reload`

>`systemctl restart docker`

>`swapoff -a`

>`systemctl start kubelet`


## worker Node Errors problem solving Same procedure follow the Master Node ##

### Master Node And Worker Node Tcp Errors Solving ###


>Unable to connect to the server: dial tcp 192.168.0.101:6443: connect: no route to host

* Solving Errors follow Command:

`sudo -i`

`swapoff -a`

`exit`

`strace -eopenat kubectl version`

`kubectl get pods`

* Errors

>the connection to the server localhost:8080 was refused - did you specify the right host or port?

* Solving command

```
mkdir -p $HOME/.kube

sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config

sudo chown $(id -u):$(id -g) $HOME/.kube/config
```

[ubuntu server iso file setup in Vm link](https://hibbard.eu/install-ubuntu-virtual-box/)

[Kubernetes deploy information link](https://blog.radwell.codes/2021/05/provisioning-single-node-kubernetes-cluster-using-kubeadm-on-ubuntu-20-04/)

