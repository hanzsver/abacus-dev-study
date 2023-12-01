# 컨버전스 사업팀 튜터링 자료

---

---

# 개요

> 웹 기술을 사실 굉장히 단순하다. 서버 또는 클라이언트에 `hmtl`, `javascript`, `css`를 브라우저가 해석 할 수 있도록 정의하고 사용자가 공개된 주소(도메인)을 통해 접근하면 의도한 페이지를 볼 수 있다. 이게 전부이다.

하지만 우리는 보다 나은 발전된 기술을 통해 사용자에게 서비스를 제공하기 위해 현대에서는 프로그래밍 환경, 기술들이 고도화 되면서 특정 목적에 의해 기술들이 정의되고 있고, 파생에 파생을 이어가고 있다.
특정 목적은 개발의 생산성, 타 플랫폼과의 연동, 임베디드 기기와의 통신, AI, 빅데이터, 그 외 특정 엔지니어링들이 있을 수 있다.

빠르게 발전하는 웹기술에서 우리는 적절한 기술들을 선택하고 학습하며 익술해지는 과정에서 원활히 소통하는 방법을 훈련 하도록 하자.

우리는 서로 무수한 관점에서 서로에게 질문을 던지고 답하며 서로 다르게 정의 될 수 있는 기술들을 준수히 공통화 될 수 있고 나아가 분업된 협업에서 원환한 소통을 통해 보다 나은 결과물을 낼 수 있을 것이라 기대한다.
> 

---

# 1장. 웹의 구성요소들에 대해 정의하고 개념을 확립하자.

### 웹의 구성 요소를 키워드로 정리 해보자.

- Http, Https
    - port : 80, 443
    
    ⇒ https http의 차이는 인증서와 공개키
    
    공개키로 암호화된 데이터를 해석 가능 (브라우저 측에서 해석 가능)
    
- Web server
    - apache
    - tomcat
    - node
- Web Client(Web browser)
    - edge
    - safari
    - chrome
    - firefox
    - other browser...
- API
    - soap
        - xml
    - rest
        - json
- Web Application
    - html
        - responsive design
        - adaptive design
    - javascript
        - es6
        - framework
            - react
            - vue
            - angular
            - angularJS
            - typescript
    - css
        - sass
        - scss
    - SPA
    - Rendering
        - SSR
        - CSR
    - database
        - DBMS
        - O-DBMS

---

> **Q.** `웹서버`의 역할을 서술 해보자.
> 
> 
> ```jsx
> A. 웹 브라우저 클라이언트로부터 HTTP 요청을 받아들이고 콘텐츠를 제공함
> ```
> 

> **Q.** `API`는 무엇이고 왜 구성되게 되었을까 서술해보자.
> 
> 
> ```jsx
> A. 소프트웨어 응용 프로그램 간에 상호 작용할 수 있도록 하는 인터페이스
> 미리 만들어둔 api를 호출해서 불러오기만 하면 되니까 재사용, 유지보수에 편리해서 개발 기간을 단축 시킬 수 있습니다.
> ```
> 

> **Q.** `웹서버`의 역할과 `웹 클라이언트`의 역할을 구분하고, 각 위치에는 어떤 것들이 구성 될 수 있는지 알아보자.
> 
> 
> ```jsx
> A. 웹 클라이언트측에서 어떤 서비스를 요청하면 웹 서버측에서 해당 서비스를 응답해주면서 통신이 이루어짐 
> 
> 구성 요소
> 	server : server-side programing language(php, jsp, java, c# ...), html, css, javascript
> 	client : html, css, javascript
> 	※ html, css, javascript는 서버에도 있을 수 있고 클라이언트에도 있을 수 있다. 이유는 무엇이고 차이점은 무엇인가?
> 		=> 어디서 렌더링 되느냐 차이..?
> ```
> 

> **Q.** 자바스크립트 규격 `ECMA Script`는 es6 버전부터 페러다임적 변화가 있었다. es6 전과 후의 버전은 무엇이 달라졌는지 서술해보자.
> 
> 
> ```jsx
> A. es6 규격으로 변화 하면서 let, const 추가/ arrow function, 백틱(``), default parameter, async/awiat, promise 같은 문법이 추가되었습니다.
> es5 기반 코드보다 간략하고 효율성 있는 코드를 만들 수 있게 되었습니다.
> ```
> 

> **Q.** 웹의 랜더링 방식은 크게 `SSR`과 `CSR`로 구분된다. 각 랜더링 방식에 대해 특징을 이해하고 서술해보자.
> 
> 
> ```jsx
> A. CSR 방식은 서버측이 HTML, JS등을 보내주면 그걸 받은 클라이언트 측에서 렌더링을 시작하는 방식으로 스크립트나 api에서 받아온 데이터가 모두 로딩이 되어야 렌더링이 완료되고 상호작용이 가능해집니다. 
> => 렌더링 완료 까지 사용자는 페이지를 볼수 없음
> - HTML,CSS,JS를 한번에 불러오기 때문에 초기 로딩이 느림
> 
> SSR 방식은 서버측에서 HTML, JS등의 렌더링 준비를 끝마친 상태로 클라이언트에게 전달하는 방식으로 클라이언트 측에서 이미 준비된 
> HTML을 바로 렌더링하고 화면에 띄운 후 JS를 다운로드(이 단계에서 사용자의 조작을 기억), 렌더링을 합니다.
> JS 까지 컴파일 끝나면 기억해둔 사용자의 조작이 실행, 상호작용이 가능해집니다.
> => 이미 HTML은 서버에서 렌더링 되었기 때문에 JS가 모두 다운로드 되지 않아도 사용자는 페이지를 볼수는 있음
> - 필요한 부분의 HTML,CSS,JS를 우선 불러오기 때문에 초기 로딩이 비교적 빠름
> - 서버에 부하가 많이 걸림
> - SEO 대응에 효과적임
> ```
> 

> **Q.** 오랜 해 동안 데이타 베이스는 `R-DBMS`만이 사용 되어 왔다. 현재에 이르러서는 객체지향 개발론, 데이터 구조론의 고도화됨에 따라 `R-DBMS`는 프로그래밍 언어와의 구조적 이질감에 효율적 사용에 많이 논의 되어 왔다. `R-DBMS`가 프로그래밍 언어들과 어떤 구조적 차이가 있는지 서술 해보자.
> 
> 
> ```jsx
> A. R-DBMS는 데이터를 저장,검색,관리 목적으로 설계되었고 프로그래밍 언더는 알고리즘 구현, 어플리케이션 개발 목적으로 설계되었습니다.
> R-DBMS는 데이터가 2차원의 테이블 형태로 표현, 나머지 언어들은 비교적 데이터 형식이 자유롭습니다.
> ```
> 

> **Q.** 현대에 `R-DBMS`를 대체할 `O-DBMS`는 무엇이고 어떤 구조를 가지고 있는지 서술 해보자.
> 
> 
> ```jsx
> A. O-DBMS는 Object타입으로 데이터를 표현하는 객체 지항 모델을 기반으로 하는 데이터베이스 시스템으로 
> 객체간의 관계, 상속, 다형성을 지원하며 복잡한 데이터 구조를 표현할 수 있습니다.
> ```
> 

---

# 2장. Node.js를 알아보자.

- **Reference**

[Introduction to Node.js | Node.js](https://nodejs.org/en/learn/getting-started/introduction-to-nodejs)

Node.js 소개

[How to install Node.js | Node.js](https://nodejs.org/en/learn/getting-started/how-to-install-nodejs)

Node.js를 설치하는 방법

[How much JavaScript do you need to know to use Node.js? | Node.js](https://nodejs.org/en/learn/getting-started/how-much-javascript-do-you-need-to-know-to-use-nodejs)

Node.js를 사용하려면 얼마나 많은 JavaScript를 알아야 합니까?

[ECMAScript 2015 (ES6) and beyond | Node.js](https://nodejs.org/en/learn/getting-started/ecmascript-2015-es6-and-beyond)

ECMAScript 2015(ES6)

[An introduction to the NPM package manager | Node.js](https://nodejs.org/en/learn/getting-started/an-introduction-to-the-npm-package-manager)

NPM 패키지 관리자 소개

[Node.js, the difference between development and production | Node.js](https://nodejs.org/en/learn/getting-started/nodejs-the-difference-between-development-and-production)

Node.js, 개발과 프로덕션의 차이점

[Node.js with TypeScript | Node.js](https://nodejs.org/en/learn/getting-started/nodejs-with-typescript)

TypeScript를 사용한 Node.js

[How to read environment variables from Node.js | Node.js](https://nodejs.org/en/learn/command-line/how-to-read-environment-variables-from-nodejs)

Node.js에서 환경 변수를 읽는 방법

---

![NODE 환경에서 NPM(Node package manager) 저장소에 있는 모듈이 개발환경(local)에 저장되는 과정](%E1%84%8F%E1%85%A5%E1%86%AB%E1%84%87%E1%85%A5%E1%84%8C%E1%85%A5%E1%86%AB%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A1%E1%84%8B%E1%85%A5%E1%86%B8%E1%84%90%E1%85%B5%E1%86%B7%20%E1%84%90%E1%85%B2%E1%84%90%E1%85%A5%E1%84%85%E1%85%B5%E1%86%BC%20%E1%84%8C%E1%85%A1%E1%84%85%E1%85%AD%2093d9111d8e4946f99126cece5f03d42b/node_npm_registry_flow.png)

NODE 환경에서 NPM(Node package manager) 저장소에 있는 모듈이 개발환경(local)에 저장되는 과정

![Javascript framework rank - 2023](%E1%84%8F%E1%85%A5%E1%86%AB%E1%84%87%E1%85%A5%E1%84%8C%E1%85%A5%E1%86%AB%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A1%E1%84%8B%E1%85%A5%E1%86%B8%E1%84%90%E1%85%B5%E1%86%B7%20%E1%84%90%E1%85%B2%E1%84%90%E1%85%A5%E1%84%85%E1%85%B5%E1%86%BC%20%E1%84%8C%E1%85%A1%E1%84%85%E1%85%AD%2093d9111d8e4946f99126cece5f03d42b/javascript_framework_rank_2023.png)

Javascript framework rank - 2023

---

# 🎓 QUIZ

1. Node.js에서 사용하는 비동기 처리 방식에 대해 설명해 보아요.
    - 비동기 방식이란 현재 진행 중인 작업의 처리가 종료되지 않아도 다음 작업을 진행할 수 있게 하는 방식을 말합니다.
        
        그렇기에 여러 요청을 동시에 수행하며 먼저 돌아온 응답부터 처리가 가능해 빠른 성능을 보여줍니다.
        
2. es6의 대표적인 문법 3가지를 말해보아요.
    - const/let, async/await, Promises, Template Literals, Arrow functions
3. Node.js는 어떤 엔진으로 빌드 되는 JavaScript 런타임일까요?
    - Chrome V8 JavaScript 엔진
4. Node.js에서 사용자가 지정한 환경변수는 어느 파일에 작성할까요?
    - .env
5. Node.js의 표준 패키지 관리자는 npm입니다. 그렇다면 npm대신 사용 가능한 패키지 관리자에는 뭐가 있을까요?
    - pnpm, yarn…