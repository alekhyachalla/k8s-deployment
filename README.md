# k8s-deployment
Kubernetes Cluster Deployment using Kube-adm

Pre-requisites:

* For Master node atleast provide 2vcpus
* All systems should have internet access
* Swap must be disabled
* SELinux must be disabled
* It is tested in CentOS 7, can be used in RHEL and Fedora

Nodes: 
 
1. One Master Node  
2. Two Worker Nodes 

On all nodes: 
 
★ Set the static IP and Hostname. 
 
# hostnamectl   set-hostname   <node-hostname> 
 
★ Disable SELinux. 
 
# setenforce 0 # sed -i --follow-symlinks 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/sysconfig/selinux # reboot 
 
★ Set the local name resolution inside ‘hosts’ file ( if DNS is not available ) 
 
#  vi  /etc/hosts 
 
<ip-of-node> <hostname-of-node> ( repeat for all 3 nodes ) 
  
  
★ Enable iptables filtering on bridge interface. 
 
# modprobe br_netfilter # echo '1' > /proc/sys/net/bridge/bridge-nf-call-iptables 



