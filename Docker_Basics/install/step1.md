공사중


기존 설치된 패키지 삭제  
`sudo apt-get remove docker docker-engine docker.io containerd runc`{{execute}}


### Install using the repository

업데이트 apt 패키지 index  
`apt-get update`{{execute}}

사전준비 (HTTPS 사용을 위한 설치)    
```
sudo apt-get -y install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```{{execute}}

Docker 공식 GPG 키 추가   
`curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`{{execute}}

Stable repo. 추가  
```
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```{{execute}}

Docker engine 설치   
`sudo apt-get update`{{execute}}
`sudo apt-get install docker-ce docker-ce-cli containerd.io`{{execute}}

설치확인  
`sudo docker run hello-world`{{execute}}

- 끝 -   (ง˙∇˙)ว
