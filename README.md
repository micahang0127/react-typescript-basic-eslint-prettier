### React Typescript ESLint Prettier Airbnb VSCode 2022

- 개념 <br>
    Lint / Linter : 코드 스타일 등을 점검하는 것<br>
    ESLint : EcmaScript + Lint. 자바스크립트 문법을 잡아주는것<br>
    Prettier : 코드 스타일을 잡아주는 코드 포맷터<br>
    즉, 오류를 잡으려면 lint, 스타일을 교정하려면 prettier에 사용<br>
    aitbnb : ESLint 로 가장 많이 쓰는 것으로 airbnb에서 정의한 자바스트립트 규칙<br>

- 설정<br>
    1.  VSCode 확장 프로그램 설치  <br>
        ESLint  <br>
        Prittier - Code formatter<br>
   
    2.  VSCode stting  <br>
         VSCode preferences -> Settings 접속<br>
   
        2-1. Javascript -> Format: Enable 체크해제(직접설정할거임)<br>
        2-2. format on save 검색 -> Editor: Format On Save 체크<br>
        : 파일저장 시 코드 eslint 적용 스타일로 변경<br>
   
        2-3. Default Formatter 검색<br>
        Editor: Default Formatter -> Pretteir - Code formatter<br>
   
    3.  react typescript project  <br>
        $ npx create-react-app react-ts-eslint-prittier --template typescript<br>
   
    4.  aitbnb eslint 설치  <br>
         $ npx install-peerdeps --dev eslint-config-airbnb<br>
        그러면 아래 모듈 설치됨 <br>
        
        ```
        // ... package.json
        "devDependencies": {
            "eslint": "^6.6.0",
            "eslint-config-airbnb": "18.2.0",
            "eslint-config-prettier": "^6.11.0",
            "eslint-plugin-import": "^2.21.2",
            "eslint-plugin-jsx-a11y": "^6.3.0",
            "eslint-plugin-prettier": "^3.1.4",
            "eslint-plugin-react": "^7.20.0",
            "eslint-plugin-react-hooks": "4.0.0",
            "prettier": "^2.0.5"
        },
        ```
            
    5.  prettier 설치 <br>
        5-1. prettier는 vscode extension으로 설치했기 때문에 따로 설치할 필요는 없지만, 프로젝트가 팀단위로 진행되거나 package.json에 확실히 명시해두고 싶다면 아래 명령어로 설치 <br>
        
            $ npm install --save-dev --save-exact prettier  <br>

        5-2. ESLint와 Prettier 규칙 충돌을 피하고 Prettier오류를 Lint에러로 보기 위해 아래 두가지 설치 <br>
        
            $ npm i -D eslint-config-prettier <br>
            $ npm i -D eslint-plugin-prettier <br>
 
        eslint-config-prettier : 불필요하거나 prettier와 출동일 일어나는 모든 ESLint의 rules를 무시. <br>
        eslint-polugin-prettier : Prettier를 ESLint의 오류로 나타나게 해주는 패키지. 즉, prettier규칙이 ESLint규칙으로 추가 된다고 볼수 있기 때분에 ESLint 하나만 실행해도 문법검사와 formatting을 함께 실행 시킬 수 있다. <br>

    6.  .eslintrc.json 파일 생성 및 작성  <br>
    
        ```
        {
            // eslint-config-airbnb의 설정을 추가하고,
            // eslint-config-prettier에서 prettier와 충돌되는 스타일 옵션을 꺼버린다
            "extends": ["airbnb", "plugin:prettier/recommended"]
        }
        ```

    7.  .prettier 파일 생성 및 작성 <br>
    
        ```
          {
                "singleQuote": true,
                "semi": true,
                "useTabs": false,
                "tabWidth": 2,
                "trailingComma": "all",
                "printWidth": 80
            }
           ```

- 패키지 및 설정값 설명  <br>
  ESLint 패키지  <br>
  eslint : 코드의 문법을 검사하는 린팅과 코드의 스타일을 잡아주는 포맷팅 기능<br>
  prettier : 코드의 스타일을 잡아주는 포맷팅 기능<br>
  @typescript-eslint/eslint-plugin : Typescript 관련 린팅규칙을 설정하는 플러그인<br>
  @typescript-eslint/parser : Typescript 를 파싱하기 위해 사용<br>
  eslint-config-airbnb : airbnb 코딩규칙을 사용(리액트 코딩규칙 포함)<br>
  eslint-config-prettier : prettier와 충돌을 일으키는 ESLint 규칙들을 비활성화 시키는 config<br>
  eslint-plugin-prettier : Prettier에서 인식하는 코드상의 포맷 오류를 ESLint 오류로 출력<br>
  eslint-plugin-react : React에 관한 린트설정을 지원<br>
  eslint-plugin-react-hooks : React Hooks의 규칙을 강제하도록 하는 플러그인<br>
  eslint-plugin-jsx-a11y : JSX 내의 접근성 문제에 대해 즉각적인 AST 린팅 피드백을 제공<br>
  eslint-plugin-import : ES2015+의 import/export 구문을 지원하도록 함<br>
<br>

- prettier  <br>
    singleQuote : single 쿼테이션 사용 여부 <br> 
    semi : 세미콜론 사용 여부  <br>
    useTabs : 탭 사용 여부  <br>
    tabWidth : 탭 너비  <br>
    trailingComma : 여러 줄을 사용할 때, 후행 콤마 사용 방식  <br>
    printWidth : 줄 바꿈 할 폭 길이  <br>
    arrowParens : 화살표 함수 괄호 사용 방식<br>

[참고]  
https://seogeurim.tistory.com/15?category=981579
