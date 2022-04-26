---
title: "[JavaScript]Front로 가기위한 나만을 위한 JS 기초다지기"
excerpt: "Front의 기초 JS!"

categories:
    - JavaScript
tags:
    - [JavaScript, Front]
# MarkDown 문법에서 목차를 우측에 보여줄지를 결정
toc: true
# 목차부분이 마우스 스크롤시 고정으로 따라오게 할지를 결정
toc_sticky: true

date: 2022-04-24
last_modified_at: 2022-04-26
---

<div style="text-align:center; color:#ffffff;">
    <h2>해당 post 는 <span style="font-weight:bold; color:#efefef">모던 자바스크립트 Deep Dive</span> 책에 있는 내용을 인용한 post 입니다.</h2>
    <div style="color:eeeeee;">
        <p>모던 자바스크립트 Deep Dive / 위키북스</p>
        <p>이웅모 지음</p>
    </div>
</div>

## Front-end
- 프론트앤드란 가장 쉽게 말해서 웹상에서 사용자들에게 보여지는 화면을 개발하는 포지션을 말합니다.    
조금 더 자세하게 설명하자면 백엔드(Back-end)에서 전해주는 데이터를 사용자들에게 보기좋게(?), 이쁘게(?) 보여주기위한 가공을 담당합니다.    
우리나라에만 있는 퍼블리셔직군은 업체에 따라 다르지만 주로 HTML, CSS 까지만 다루고 프론트부터 JavaScript를 만지게 됩니다.   
사실 더 세분화하면 끝도 없지만 이제 겨우 경력 1년이 조금넘은 비전공자인 저로써는 여기까지밖에 구분이 안되는 상황입니다.    
그렇다고 프론트와 백,퍼블리셔가 무조건 자기가 하는 포지션의 언어만 알고 있다고 다 할 수 있다고는 생각하지 않습니다.   
각 포지션들이 다른 포지션은 어떤식으로 진행되는지는 파악하고 있어야 협업이 가능하다고 생각합니다.



## 그래서 JavaScript는?
- JavaScript는 객체 기반의 프로그래밍 언어이다. 이 언어는 웹 브라우저 내에서 주로 사용하며,   
**다른 응용프로그램의 내장 객체에도 접근할 수 있는 기능을 가지고 있다. 또한 Node.js와 같은 런타임 환경과 같이 서버 프로그래밍에도 사용되고 있다.**    
자바스크립트는 본래 넷스케이프 커뮤니케이션즈 코퍼레이션의 브렌던 아이크(Brendan Eich)가 처음에는 모카(Mocha)라는 이름으로,   
나중에는 라이브스크립트(LiveScript)라는 이름으로 개발하였으며, 최종적으로 자바스크립트가 되었다.    
자바스크립트가 썬 마이크로시스템즈의 자바와 구문이 유사한 점도 있지만, 이는 사실 두 언어 모두 C 언어의 기본 구문에 바탕을 뒀기 때문이고,    
자바와 자바스크립트는 직접적인 연관성은 약하다.    
이름과 구문 외에는 자바보다 셀프나 스킴과 유사성이 많다.    
자바스크립트는 ECMA스크립트(ECMAScript)의 표준 사양을 가장 잘 구현한 언어로 인정받고 있으며   
 ECMAScript 5(ES5)까지는 대부분의 브라우저에서 기본적으로 지원되었으나 ECMAScript 6 이후부터는 브라우저 호환성을 위해 트랜스파일러로 컴파일된다.

 [출처 : 위키백과](https://ko.wikipedia.org/wiki/%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8){:_target="_blank"}

 - JavaScript는 다른 응용프로그램 내장 객체에도 접근할 수 있는 기능을 가지고 있다고 설명이 되 있다.   
가장 소스가 많이 있는 JSP 기준으로 설명하면 JSP 내에서 선언하지 않고 사용할 수 있는 객체를 JS로 접근이 가능하다는 것이다.



## JavaScript 의 장점
- 그렇다면 왜 JavaScript를 사용하는지 장점을 알아보겠습니다. 아무리 좋다고 해도 이유는 알고 있어야 하니까요.   
간단한게 JAvaScript의 장점얼 알아보면 JavaScript는 먼저 다른 언어에 비해 컴파일하는 과정이 없기 때문에   
다른 언어에 비해 시간이 적게 소요되며, 클라이언트 스크립트기 때문에 서버 연결에 드는 시간을 절약할 수 있습니다.    
또한 JavaScript는 비교적 단순한 언어에 속하기 때문에 처음 진입장벽이 낮으며 언어의 구조 또한 쉽습니다.   
JavaScript의 실행 순서는 코드의 위에서 아래로 순차적으로 실행되는 것이 기본이기 때문입니다.
그리고 JavaScript는 프론트와 백 다양한 포지션에서 활용이 가능한 언어입니다.


## JavaScript의 단점
- 빠른 속도와 낮은 진입장벽을 가지고 있는 JavaScript도 무조건적으로 장점만 있는 것은 아닙니다.    
진입장벽이 낮다보니 JavsScript Code는 사용자에게 보여지는 부분이기 때문에 누군가가 악의적으로 코드를 사용 할 수 있으며   
JavaScript를 통하여 악성코드를 웹 사이트에 심는 것도 매우 쉽습니다.   
다양한 브라우저에서 JavaScript를 지원하지만 각각의 브라우저들이 JavaScript를 해석하는 방법이 다르기 때문에   
 이 부분 또한 프로젝트 배포 전에 확인해야 할 사항중 하나입니다.   
또한 JavaScript는 단일 상속만 지원하며 만약 작성한 JavaScript 코드 중에 중간에 Error가 나면  
그 즉시 모든 JavsScript의 렌더링이 중지되는 단점이 있습니다.


## 변수
- 변수란 무엇이며 왜 사용하는가?   
**변수(variable)는 하나의 값을 저장하기 위해 확보한 메모리 공간 자체 또는 그 메모리 공간을 식별하기 위해 붙인 이름을 말한다.(모던 자바스크립트 Deep Dive 중)**  
현재 독학으로 공부하고 있는 책에 나와있는 내용입니다. 해당 책에서는 이러한 글과 함께 조금 더 쉬운 설명이 있는데 **변수는 프로그래밍 언어에서 값을 저장하고 참조하는 메커니즘으로,**    
**값의 위치를 가리키는 상징적인 이름이다.**  라고 부연설명이 되어 있습니다. 개발자가 작성한 변수는 컴퓨터가 읽을 수 있는 프로그래밍 언어로 변형된 후 메모리 공간의 주소로 치환된 후 실행됩니다.


## 변수 선언 시 네이밍 규칙
- 변수이름을 정할 때 따로 지정이 되어 있거나 반드시 사용을 해야하만 하는 네이밍은 없습니다. 개인이 혼자서 진행하는 프로젝트라면 개인이 기억할 수 있는 혹은 개인이 파악할 수 있는 규칙을 기준으로 변수명을 지정합니다.
혹은 팀 단위 이상의 프로젝트를 진행할 때는 프로젝트 시작 전 프론트와 백 등 다양한 언어의 네이밍 규칙을 문서화하여 작업을 진행하게 됩니다.   
변수명은 자유롭게 지을 수 있지만 몇가지 특별한 규칙이 있습니다. 만약 이 특별한 규칙을 지키지 않는다면 JavaScript는 Error만 뿜어내게 됩니다.
    - 1. 변수명에 사용가능한 특수문자는 _(언더스코어) 와 $(달러 기호) 뿐이다.
    - 2. 변수명의 첫 시작은 문자, _, $ 로만 가능하다. 숫자로는 시작할 수 없다.
    - 3. JavaScript의 예약어로는 변수를 만들 수 없다.   
    
```javascript
    // 사용가능
    var _test = 1;
    var $test = 1;
    var test1 = 1;
    var $test1 = 1;
    var test_1 = 1;

    // 사용불가
    var 1test = 1;
    var !test = 1;
    var @test = 1;
    var test 1 = 1;
```

---

<div style="width:100%;">
<table class="table_type_1">
    <colgroup>
        <col width="20%">
        <col width="20%">
        <col width="20%">
        <col width="20%">
        <col width="20%">
        <col width="20%">
    </colgroup>
    <thead>
        <tr>
            <th colspan="6">JavaScript 예약어 종류</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>break</td>
            <td>case</td>
            <td>catch</td>
            <td>class</td>
            <td>const</td>
            <td>continue</td>
        </tr>
        <tr>
            <td>debugger</td>
            <td>default</td>
            <td>delete</td>
            <td>do</td>
            <td>else</td>
            <td>export</td>
        </tr>
        <tr>
            <td>extends</td>
            <td>false</td>
            <td>finally</td>
            <td>for</td>
            <td>function</td>
            <td>if</td>
        </tr>
        <tr>
            <td>import</td>
            <td>in</td>
            <td>instanceof</td>
            <td>new</td>
            <td>null</td>
            <td>return</td>
        </tr>
        <tr>
            <td>super</td>
            <td>switch</td>
            <td>this</td>
            <td>throw</td>
            <td>true</td>
            <td>try</td>
        </tr>
        <tr>
            <td>typeof</td>
            <td>var</td>
            <td>void</td>
            <td>while</td>
            <td>with</td>
            <td>yield</td>
        </tr>
    </tbody>
</table>
</div>


- 위의 테이블 목록은 JavaScript에서 쓰이는 예약어 종류들입니다. 위의 예약어들은 단독적으로 변수명 지정이 불가능 합니다. ES5부터 변수(식별자)를 만들 때 유니코드 문자를 허용하므로 한글이나 일본어 등 다양한 언어로 변수 설정이 가능하지만 추후 개발과 유지보수를 생각했을 때에는 사용하지 않는 것이 바람직합니다.   
또한 변수명은 알파벳 대·소문자를 구분합니다.

---

<div style="width:100%;">
<table class="table_type_1">
    <colgroup>
        <col width="20%">
        <col width="20%">
        <col width="20%">
        <col width="20%">
        <col width="20%">
        <col width="20%">
    </colgroup>
    <thead>
        <tr>
            <th colspan="6">ECMAScript 6 이후에 추가될 예정인 예약어 종류</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>await</td>
            <td>enum</td>
            <td>implements</td>
            <td>package</td>
            <td>protected</td>
            <td>interface</td>
        </tr>
        <tr>
            <td>private</td>
            <td>public</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
    </tbody>
</table>
</div>

- 위의 테이블에 ECMAScript 6 이후에 추가될 예정인 예약어 목록의 경우 식별자로 사용이 가능하나 strict mode에서는 사용이 불가능 합니다.

---

<div style="width:100%;">
<table class="table_type_1">
    <colgroup>
        <col width="25%">
        <col width="25%">
        <col width="25%">
        <col width="25%">
    </colgroup>
    <thead>
        <tr>
            <th colspan="6">미리 정의된 전역 변수와 전역 함수</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>argument</td>
            <td>Array</td>
            <td>Boolean</td>
            <td>Date</td>
        </tr>
        <tr>
            <td>decodeURI</td>
            <td>decodeURIComponent</td>
            <td>encodeURI</td>
            <td>encodeURIComponent</td>
        </tr>
        <tr>
            <td>Error</td>
            <td>eval</td>
            <td>EvalError</td>
            <td>Function</td>
        </tr>
        <tr>
            <td>Infinity</td>
            <td>isFinite</td>
            <td>isNaN</td>
            <td>JSON</td>
        </tr>
        <tr>
            <td>Math</td>
            <td>NaN</td>
            <td>Number</td>
            <td>Object</td>
        </tr>
        <tr>
            <td>parseFloat</td>
            <td>parseInt</td>
            <td>RangeError</td>
            <td>ReffernceError</td>
        </tr>
        <tr>
            <td>RegExp</td>
            <td>String</td>
            <td>SyntaxError</td>
            <td>TypeError</td>
        </tr>
        <tr>
            <td>undefined</td>
            <td>URIError</td>
            <td></td>
            <td></td>
        </tr>
    </tbody>
</table>
</div>

- 위의 표는 JavaScript에서 미리 정의된 전역 변수와 전역 함수 목록입니다.   
이 이름들 역시 식별자로 사용하지 않도록 합니다.   
해당 목록에 있는 이름들은 사용해도 오류가 출력되지는 않지만   
JavaScript가 가진 본래 기능을 사용할 수 없게 됩니다.

---

```javascript
    const Test = 1;
    const test = 2;
```
위에 두개의 변수 'Test' 와 'test' 는 온전히 다른 변수입니다.

- 변수를 선언할 때 변수의 시작부분 혹은 끝 부분에 주석처리를 한 후 어떤 용도로 만들었는지 등 간단한 설명을 기입해 놓으면 해당 코드를 처음보는 사람도 조금 더 빨리 코드를 이해할 수 있게됩니다. 디만 이 주석처리의 경우 사람마다 다르기 때문에 주의해서 사용해야 합니다.



## 변수선언 일관성을 위한 작성법
- 네이밍 컨벤션(naming convention)은 하나 이상의 영어단으로 구성된 식별자를 만들 떄 가독성이 좋게   
단어를 한눈에 구분하기 위해 규정한 명명 규칙입니다. 네이밍 컨벤션 유형은 4가지가 있으며 상황에 맞는 혹은 회사에 맞는 네이밍 컨벤션을 사용하면 됩니다.

```javascript
    <!-- 카멜 케이스 (camleCase) -->
    var firstName;

    <!-- 스네이크 케이스 (snake_case)-->
    var first_name;

    <!-- 파스칼 케이스 (FirstChil) -->
    var FirstName;

    <!-- 헝가리언 케이스 (typeHungarianCase) -->
    var strFirstName;
    var $elem = document.getElementById('ID이름');
    var obserable$ = fromEvent(document.'click');
```

## 표현식과 문
- 값(value) : 값은 식(표현식(expression))이 평가(evaluate)되어 생성된 결과를 말한다. 평가란 식을 해석해서 값을 생성하거나 참조하는 것을 의미한다.
- 리터럴(literal) : 리터럴은 사람이 이해할 수 있는 문자 또는 약속된 기호를 사용해 값을 생성하는 표기법(notation)을 말한다.

|리터럴 종류|예시|비고|
|-----|-----|-----|
|정수 리터럴|100||
|부동소수점 리터럴|10.5|
|2진수 리터럴|0b01000001|0b로 시작|
|8진수 리터럴|0o101|ES6에서 도입.<br/>0o로 시작|
|16진수 리터럴|0x41|ES6에서 도입.<br/>0x로 시작|
|문자열 리터럴|'Hello'<br/>'World||
|불리언 리터럴|true<br/>false||
|null 리터럴|null||
|undefined 리터럴|undefined||
|객체 리터럴|{ name: 'Kim', address: 'Suwon'}||
|배열 리터럴|[1, 2, 3]||
|함수 리터럴|function() {}||
|정규 표현식 리터럴|/[A-Z]+/g||

- 표현식(expression) : 표현식은 값으로 평가될 수 없는 문(statement)이다. 즉, 표현식이 평가되면 새로운 값을 생성하거나 기존 값을 참조한다.

```javascript
    var score = 100;
    // 100은 리터럴이자 표현식

    var score = 50 + 50;
    // 50 + 50 은 리터럴과 연산자로 이루어져 있다, 하지만 50 + 50 도 평가되어 숫자 값 100을 생성하므로 표현식이다.

    score;
    // 변수 식별자를 참조하면 변수값으로 평가된다. 식별자 참조는 값을 생성하지는 않지만 값으로 평가되므로 표현식이다.
```

## JavaScript 의 데이터 타입
- ES6의 JavaScript에서는 7개의 데이터 타입을 제공한다. 이 데이터 타입은 원시 타입(primitive type)과 객체 타입(object/reference type)으로 분류할 수 있다.

|구분|데이터 타입|설명|
|----|-----|-------|
|원시 타입|숫자(number)타입|숫자. 정수와 실수 구분 없이 하나의 숫자 타입만 존재|
|원시 타입|문자열(string)타입|문자열|
|원시 타입|불리언(boolean)타입|논리적 true(참)과 false(거짓)|
|원시 타입|undefined 타입|var 키워드로 선언된 변수에 암묵적으로 할당되는 값|
|원시 타입|null 타입|값이 없다는 것을 의도적으로 명시할 때 사용하는 값|
|원시 타입|심벌(stymbol)타입|ES6에서 추가된 7번째 타입|
|객체 타입||객체, 함수, 배열 등|


## 숫자(number) 타입
- C나 JAVA의 경우 정수와 실수를 구분해서 int, long, float, double 등과 같은 다양한 숫자타입을 제공하지만   
JavaScript에서는 오직 하나의 숫자 타입만 존재합니다.   
즉 JavaScript에서는 모든 수를 실수로 처리하며, 정수만 표현하기 위한 데이터 타입은 JavaScript에선 별도로 존재하지 않습니다.
```javascript
    // 예시
    var inteeger = 10;    // 정수
    var double = 10.12;   // 실수
    var negative = -20;   // 음의 정수
``` 

- 또한 JavaScript는 2진수, 8진수, 16진수를 표현하기 위한 데어터 타입을 제공하지 않기 때문에    
아래의 코드들의 값들을 console.log 로 확인을 해보면 모두 10진수로 해석됩니다.
```javascript
    var binart = 0b01000001;  // 2진수
    var octal = 0o101;        // 8진수
    var hex = 0x41;           // 16진수

    console.log(blnart);
    // 65;
    console.log(octal);
    // 65;
    console.log(hex);
    // 65;
    console.log(blanrt === octal);
    // true;
    console.log(octal === hex);
    // true;
```

- JavaScript의 숫자 타입은 정수만을 위한 타입이 따로 없고 모든 수를 실수로 처리하기 때문에    
정수로 표시되는 수 끼리 나누더라도 실수가 나올 수 있습니다.
```javascript
    console.log(1 === 1.0);
    // true;
    console.log(4 / 2);
    // 2;
    console.log(3 / 2);
    // 1.5;
```

- JavaScript의 숫자 타입에서는 추가적으로 3가지 특별한 값도 표현할 수 있습니다.
    - Infinity : 양의 무한대
    - -Infinity : 음의 무한대
    - NaN : 산술 연산 불가(not-a-number)
- 단 주의할 점은 JavaScript는 대·소문자를 구분하기 때문에 NaN을 NAN, Nan, nan 등 처럼 표기하게 되면 Error가 발생합니다.


## 문자열(string) 타입
- 문자열 타입은 말 그대로 텍스트 데이터를 나타내는데 사용됩니다. 문자열은 0개 이상의 16비트 유니코드 문자 (UTF-16)의 집합으로 전 세계 대부분의 문자를 표현할 수 있습니다.
- 문자열을 표현할 때는 작은따옴표(''), 큰따옴표(""), 백틱(``) 으로 텍스트를 감싸주어 사용합니다.    
백틱의 경우는 ES6에서 사용됩니다.



## 불리언(boolean) 타입
- 불리언 타입은 오직 **논리적인 참(true) 과 거짓(fasle)만 존재** 합니다.



## undefined 타입
- undefined 타입의 값은 **undefined** 가 유일합니다.
- var 키워드로 선언한 변수는 암묵적으로 undefined로 초기화 되는데, 이는 변수 선언에 의해 확보된 메모리 공간을 처름 할당이 이루어 질 때 까지 빈 상태로 두지 않고 JavaScript엔진이 undefined로 초기화 하기 때문입니다.    
즉 변수를 선언한 이후 값을 할당하지 않은 변수를 참조하면 undefined가 반환됩니다.



## null 타입
- null 타입의 값도 undefined 처럼 null 이 유일합니다.
- null 또한 대·소문자를 구분하는 JavaScript 때문에 Null, NULL 등과 다릅니다.    
만약 변수에 null을 할당하면 변수가 이전에 참조하던 값을 더 이상 참조하지 않겠다는 의미이며,   
이는 이전에 할당되어 있던 값에 대한 참조를 명시적으로 제거하는 것을 의미합니다.   
JavaScript엔진은 누구도 참조하지 않는 메모리 공간에 대해 가비지 콜렉션을 수행합니다.   
또한 함수가 유요한 값을 반환할 수 없는 경우에도 명시적으로 null 을 반환하기도 합니다.
```javascript
    // 유요한 값을 반환할 수 없는 경우
    var foo = 'Kim';

    foo = null;
```



## 심벌(Symbol) 타입
- 심벌 타입은 ES6에서 추가된 7번째 타입으로써 변경이 불가능한 원시 타입의 값 입니다.
- 심벌 타입은  **다른 값과 중복되지 않는 유일무이한 값** 이기 때문에 주로 이름이 충돌할 위험이 없는 객체의 유일한 프로퍼티 키를 만들기 위해 사용됩니다.
- 심벌 이외의 원시 값은 리터럴을 통해 생성하지만 특별하게 심벌의 경우는 **Symbol** 함수를 호출해서 생성합니다.   
이 때 생성된 심벌 값은 외부에 노출이 되지 않으며, 다른 값과 절대 중복되지 않는 유일무이한 값 입니다.
```javascript
    // 심벌 값 생성
    var key = Symbol('key');
    console.log(typeof key);
    // symbol;

    // 객체 생성
    var obj = {};

    obj[key] = 'value';
    console.log(obj[key]);
```
