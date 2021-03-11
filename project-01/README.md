# 설치 및 실행

### 1. nodejs를 설치한다.
### 2. node-red를 설치한다.
```bash
# 글로벌 설치
$ npm install -g --unsafe-perm node-red

# 프로젝트 폴더로 이동 후 명령어 실행 - 선택사항: node-red 실행 후 대시보드에서 설치해도됨 4.번 참고
$ cd project-01
$ npm install node-red-dashboard
```

### 3. node-red 실행
```
$ node-red
```

### 4. node-red 접속
`http://localhost:1880`으로 접속  
접속 후 node-red 대쉬보드에서 오른쪽 상단 메뉴 클락 -> 팔렛트 관리 -> 팔렛트 -> 설치가능한 노드에서 -> node-red-dashboard 참고  

### 5. node-red 데몬 서비스 관리 - (데몬 관리는 리눅스에서만 적용)
```bash
node-red-stop # Node-RED 를 정지
node-red-start # Node-RED 를 시작
node-red-restart # Node-RED 를 재시작
node-red-log # Node-RED 로그 출력
sudo systemctl enable nodered.service # Node-RED를 매번 부팅할 때마다 자동 실행 시킵니다.
sudo systemctl disable nodered.service # 부팅시 자동실행을 비활성화 한다
```
### 6. node-red 삭제
```bash
$ sudo npm -g remove node-red
$ sudo npm -g remove node-red-admin
$ rm -R ~/.node-red
```

