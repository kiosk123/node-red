# nodeRED project 사용법

프로젝트 별로 관리하는 방법을 알아본다.  
`.node-red`디렉터리는 git을 이용해서 버전 관리를 해주는 것이 좋다.

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

