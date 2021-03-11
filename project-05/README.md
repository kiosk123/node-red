# node-red에 password 설정하기
node-red 실행 후 `http://localhosts:1880`으로 접근시 누구나 주소만 알면 접근 가능하기 때문에  
비밀번호를 설정할 필요가 있음

### settings.js 수정하기
node-red 디렉터리의 setting.js 파일을 수정한다.  
파일을 열고 설정이 필요한 부분의 주석을 제거한 후 username 부분에 사용하고 싶은 계정명을 설정한다.  
password는 파일에서 바로 수정할 수 없고 npm 모듈을 설치한 후 수정한다.
```bash
$ cd ~/.node-red
$ vi settings.js

# 이부분 주석 해제
adminAuth: {
    type: "credentials",
    users: [{
        username: "admin", # 원하는 이름으로 변경
        password: "$2a$08$zZWtXTja0fB1pzD4sHCMyOCMYz2Z6dNbM6tl8sJogENOMcxWV9DN.",
        permissions: "*"
    }]
},
```

password를 수정하기 위해 node-red-admin을 설치한다.
```bash
$ npm install -g node-red-admin
```

설치후 다음의 명령어를 입력후 password를 입력한 후 엔터키를 누르고 출력된 해쉬코드 복사한다.
```bash
$ node-red-admin hash-pw
$2b$08$PSB3qb/ipZ388SEEBuX9QeDsEaaoxP9Woctd7X.uYwBFtwqe2KKhu
```

settings.js 파일에서 위에서 주석 해제한 부분의 password 부에 붙여넣고 저장한다.
```json
adminAuth: {
    type: "credentials",
    users: [{
        username: "admin", # 원하는 이름으로 변경
        password: "여기에 붙여넣기",
        permissions: "*"
    }]
},
```