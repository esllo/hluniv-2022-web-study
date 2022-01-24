# 웹 

HTML + CSS + JAVASCRIPT 의 조합



## HTML

웹의 구조를 나타내는 언어

제목, 단락, 목록, 표 등의 구조적 의미와 또는 링크, 인용 등의 구조적 문서를 만들 수 있습니다.



#### 구조

```html
<!DOCTYPE html>
<html>
    <head>
        <!-- ... -->
    </head>
    <body>
        <!-- ... -->
    </body>
</html>
```



## CSS

마크업 언어의 스타일을 표현하는 언어

웹에서 HTML이 구조를 만들면 CSS로 꾸미는 역할을 합니다.

색상, 여백, 모서리, 테두리, 애니메이션 등의 다양한 속성을 추가할 수 있습니다.



#### 구조

```css
*{
    padding: 0;
    margin: 0;
}
.class {
    background: #000000;
}
#id {
    color: red;
}
/* ... */
```



## JAVASCRIPT

객체 기반의 스크립트 언어

ECMA 스크립트의 표준을 따르며 웹에서 주로 동작의 역할을 맡습니다.

페이지의 컨텐츠를 제어하거나 데이터를 관리할 수 있습니다.



#### 구조

```javascript
const hello = "hello world!"

function printHello(){
    console.log(hello);
}

printHello();
```





# 웹 페이지 호스팅

웹 페이지는 기본적으로 .html 확장자를 사용하며 http 또는 https 프로토콜로 통신하는 서버에서 호스팅합니다.

주로 아래의 서버를 사용합니다.

- Apache
- Nginx



이번 멘토링에서는 Nginx를 통해 호스팅되는 서버를 개인별로 제공할 예정이며 **web{num}.esllo.com** 형태의 주소로 제공됩니다.



## VSCODE 세팅

#### vscode 설치 : https://code.visualstudio.com/



#### vscode 플러그인

- Remote - SSH

  SSH를 통해 vscode에서 작업할 수 있도록 해주는 플러그인

  

- Remote - SSH: Editing Configuration Files

  Remote - SSH를 도와주는 플러그인

  

- **[선택]** Live Server 

  로컬 서버를 실행하기 위한 플러그인



#### Remote - SSH 설정

1. Remote Explorer 탭에서 상단에 **SSH Targets** 선택

2. **+** 버튼을 눌러서 `ssh {받은 아이디}@web.esllo.com` 입력 후 엔터

3. `C:\Users\{윈도우 유저 이름}\.ssh\config` 또는 기타 config 파일 선택

4. `ctrl`+`shift`+`p` 를 누르고 ssh config를 타이핑 후 `Open SSH Configuration File...` 선택

5. 위에서 선택한 config 파일 열기

6. 아래 형태로 되어있는지 확인

   ```
   Host {web.esllo.com 또는 사용할 호스트 이름}
     HostName web.esllo.com
     User {받은 아이디}
   ```

   

#### Remote - SSH 연결

1. `ctrl`+`shift`+`p` 를 누르고 ssh connect 타이핑 후 `Connect to Host`와 `Connect Current Window ...` 중 선택
2. `web.esllo.com` 선택 후 패스워드 입력
3. Explorer에서 Open Folder 선택 후 `/home/{받은 아이디}` 선택 후 패스워드 입력



### node 환경 사용 시 

node환경 사용 시 특정 폴더에서 http-server 패키지를 사용하여 서버를 열 수 있습니다.

1. http-server 패키지를 `npm install -g http-server` 또는 `yarn global add http-server` 를 통해 설치합니다.

2. 파일 탐색기에서 원하는 폴더에 들어간 후 주소창에 cmd 입력 후 엔터를 칩니다.

3. cmd 창이 열리면 http-server -p {포트번호} 를 통해 서버를 열 수 있습니다. -p 는 생략 가능하며 기본으로 8080 포트가 사용됩니다.
4. 브라우저에서 localhost:{포트 번호} 를 통해 실행할 수 있습니다.
