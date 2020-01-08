###Kubernetes adalah platform luas untuk mengelola kluster penampung, yang berasal dari Google. Seperti kebanyakan perangkat lunak server dari Google, Kubernetes unggul dalam skalabilitas.

#update repo
sudo apt-get update

#update certificate
sudo apt-get apt install apt-transport-https ca-certificates curl software-properties-common -y

#tambahkan key untuk kubernetes
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -

#tambahkan repo kubernetes
cat <<EOF >/etc/apt/sources.list.d/kubernetes.list
deb http://apt.kubernetes.io/ kubernetes-xenial main
EOF

#update repo kembali
sudo apt-get update

#install kubernetes
apt install kubelet kubeadm kubernetes-cni -y

#setup Kubernetes Master
sysctl net.bridge.bridge-nf-call-iptables=1

#disable swap
swapoff -a

#inisialisasi kubernetes
kubeadm init --pod-network-cidr=10.244.0.0/16 --apiserver-advertise-address=192.168.88.100 --kubernetes-version stable-1.9

#Jika berhasil maka akan muncul output seperti berikut.
Your Kubernetes master has initialized successfully!


