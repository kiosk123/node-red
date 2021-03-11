# nodeRED project 사용법

프로젝트 별로 관리하는 방법을 알아본다.  
node-red 프로젝트는 `~/.node-red/<프로젝트명>` 형태로 관리되며 프로젝트 생성시 git에 의해서 버전 컨트롤이 된다.  
그러므로 먼저 git이 설치되어 있어야 한다.  

### 1. node-red 파일의 위치로 이동
`<계정 홈 디렉터리>/.node-red`이 node-red 파일이 위치한다.
```bash
$ cd ~/.node-red
```
### 2. settings.js 수정
` ~/.node-red `로 이동 후 `settings.js`파일을 편집기로 오픈한다.  
파일 맨아래로 내려가서 `enabled: true`로 변경하고 저장한다.
```js
 // Customising the editor
editorTheme: {
    projects: {
        // To enable the Projects feature, set this value to true
        enabled: true
    }
}
```

### 3. node-red 재실행
node-red를 재실행하여 `settings.js`의 설정을 적용하자.  
그리고 `localhost:1880`으로 접속시 프로젝트를 생성할 수 있는 메뉴가 뜨게 된다.

### 4. 프로젝트 생성
로컬 프로젝트를 생성할 수도 있고, github에 공유되어 있는 프로젝트를 불러와서 사용할 수도 있다.

