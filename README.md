# Docker 를 조금씩 알아가며 기록.

### 기존에 설치된 도커 커뮤니티 에디션과 도커 엔진을 제거하는 방법.
```
    sudo apt-get remove docker docker-engine docker.io containerd runc
```


### 우분투 리눅스 패키지 관리자의 도커 공식 저장소를 추가하기 전 필요 패키지 먼저 설치.

```
    sudo apt-get update

    sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```

### 도커 패키지 저장소를 인증하기 위한 인증키 추가.
```
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

### 인증키가 잘 설치됐는지 확인
```
    sudo apt-key fingerprint 0EBFCD88
```


### 안정 버젼을 제공하는 저장소를 추가 하기.
```
    sudo add-apt-repository \
    "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) \
    stable"
```

### 새로 추가된 저장소의 패키지 정보를 업데이트/도커 엔진 패키지  설치.
```
    sudo apt-get update
    sudo apt-get install docker-ce docker-ce-cli containerd.io
```

### 위 방법을 사용한 경우 `docker compose`를 별도로 설치해야 한다.
```
    sudo curl -L "https://github.com/docker/compose/releases/download/1.27.4/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

    sudo chmod +x /usr/local/bin/docker-compose
```
- 만약 다른 버젼을 설치하고 싶다면 위 명령의 `1.27.4` 부분을 원하는 버젼으로 수정하면 된다.



위 방법으로 도커 엔진과 도커 컴포즈의 설치가 끝 난다.


```
    docker version
    sudo docker version
    
    docker-compose version
    sudo docker-compose version
```

도커 버젼을 확인하고 도커가 잘 설치되었는지 확인해 보자.


위 부분만 따라하면 도커 설치는 금방 되는것 같다.

외울것 아니라 참고,활용하여 사용하면 될 것 같다.

