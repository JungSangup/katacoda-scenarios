이제 도커 볼륨(Volume)을 이용해서 데이터를 유지하는 방법을 알아보겠습니다.

우리 샘플 애플리케이션(Todo List Manager)는 SQLite database를 사용하고 있습니다.  
데이터는 `/etc/todos/todo.db` 에 파일로 저장이 되고 있구요.

이제 도커 볼륨을 이용해서 데이터가 저장되는 위치를 호스트의 경로로 바꿔보겠습니다.

먼저 도커 볼륨을 하나 생성합니다.
`docker volume create todo-db`{{execute}}

그리고, 방금 생성한 볼륨을 우리 애플리케이션의 데이터 저장경로로 마운트해서 실행해 보겠습니다.
`docker run --detach --publish 3000:3000 --volume todo-db:/etc/todos --name my-todo-manager rogallo/101-todo-app:1.0.0`{{execute}
`--volume todo-db:/etc/todos`에서 콜론(:)앞은 volume의 이름을, 뒤는 컨테이너의 경로를 적어줍니다.

`Display 3000`탭을 클릭해서 애플리케이션으로 접속하고 오늘 할 일을 몇 개 적어볼까요?

그리고, 컨테이너를 삭제합니다.
`docker rm --force my-todo-manager`{{execute}}
> 컨테이너는 생성할때 --name 옵션으로 이름을 정하면, 이후에 이 이름을 이용할 수 있습니다.

그리고, 똑 같이 다시 실행해 볼까요?
`docker run --detach --publish 3000:3000 --volume todo-db:/etc/todos --name my-todo-manager rogallo/101-todo-app:1.0.0`{{execute}

어떤가요?
오늘 할 일 목록이 그대로 남아있나요?

이제, 좀 제대로 된 애플리케이션이 된 것 같네요.... (ง˙∇˙)ว
