자주 사용되는 도커 명령어를 알아보겠습니다.

​     

pull > images > run (-it, -d) > ps > exec > stop > restart > rm > rmi
tag > push


먼저 현재 컨테이너와 이미지를 모두 정리하고 시작할게요.
`docker rm -f $(docker ps -aq)`{{execute}}
`docker rmi -f $(docker images -aq)`{{execute}}
참고로 -f 옵션은 강제로 삭제를 하는 옵션이니 주의해서 사용해야 합니다.

도커이미지를 검색하는 명령어는 `docker search`입니다.
도커허브에서 Ubuntu 이미지를 찾아볼까요?
`docker search ubuntu`{{execute}}

https://hub.docker.com/ 에서도 한번 검색을 해보세요.

두 가지 결과가 어떤지 비교해보세요.

이제 ubuntu 이미지를 다운로드(pull) 해 보겠습니다.

`docker pull ubuntu`{{execute}}

`docker pull ubuntu:18.04`{{execute}}


`docker images`{{execute}}
