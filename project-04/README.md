# mongodb compass 설치
mongodb compass는 mongodb 시각화 도구이다.  
사용 버전은 1.26.0이다.

### mongodb compass 설치 및 실행 
1. mongodb compass zip파일을 [다운로드](https://www.mongodb.com/try/download/compass) 받는다.  
2. 다운받은 파일 압축을 풀고 MongoDBCompass.exe를 실행한다.
3. New Connection의 Paste your connection string 부분에 다음과 같은 형식으로 mongodb 연결 정보를 설정한다.  
```
mongodb://[username:password@]host1[:port1][,...hostN[:portN]][/[defaultauthdb][?options]]

ex)
mongodb://mongodb0.example.com:27017
```

### mongodb 비밀번호 설정
mongodb가 설치되어 있는 서버에 접속하여 mongo 디비에 접속한다.
```bash
$ mongo

# mongdb에 생성되어 있는 스키마 확인
> show dbs 

# admin 스키마로 이동
> use admin 

# 계정 생성 - 아이디 admin / 비번 1234 , 권한은 모든 데이터 베이스를 사용하고 readWrite 할수 있게 설정한다
> db​.createUser({
    user: "admin",
    pwd: "1234",
    roles: [ { role: "userAdminAnyDatabase", db: "admin" }, "readWriteAnyDatabase" ]
  })

# 작업 후 빠져나온다.
> exit
```

#### mongod.conf를 편집한다. - mongodb.conf 일수도 있음 (CentOS7 기준)

```bash
$ sudo vi /etc/mongod.conf

#security
setParameter:
  enableLocalhostAuthBypass: false
security:
  authorization: enabled
```

위와 같은 설정 값이 아닌 다음과 같이 auth가 나올경우 아래와 같이 auth를 수정한다.
```bash
# Turn on/off security.  Off is currently the default
#noauth​ = true
auth = true
```

mongodb 데몬을 재시작한다. 
```bash
$ sudo systemctl restart mongod
```


