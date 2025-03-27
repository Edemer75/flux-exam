### Install sshd
```
sudo apt install openssh-server
```
### Add ssh-key
```
echo id_rsa.pub >> ~/.ssh/authorized_keys
```
### Create local git repo
```shell
mkdir ~/git/flux-exam
cd ~/git/flux-exam
git init
gcb flux-exam
```
### Bootstrap flux to minikube clusterqs
```
flux bootstrap git \   
  --url=ssh://vwinkler@10.20.30.106:22/home/vwinkler/git/flux-exam \
  --branch=flux-exam \
  --private-key-file=/home/vwinkler/.ssh/id_rsa \
  --path=clusters/minikube
```
