샘플 애플리케이션을 실행해 보겠습니다.



앞에서는 컨테이너 이미지를 만들었습니다.

이번에는 이 이미지를 실제 컨테이너로 실행(run)해 보겠습니다.



`docker run -dp 3000:3000 docker-101`{{execute}}




잘 실행되고 있는지 볼까요?

`docker ps -a`{{execute}}



`docker-101` 이 보이면 정상입니다.    (ง˙∇˙)ว    



이제 `Terminal`의 `Display 3000` 탭을 눌러보세요.



여러분의 ToDo List Manager 애플리케이션이 잘 동작하나요?



축하합니다!!! 