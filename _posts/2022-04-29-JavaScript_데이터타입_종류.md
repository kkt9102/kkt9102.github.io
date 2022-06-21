---
title: "[JavaScript]Front로 가기위한 나만을 위한 JS 기초다지기-데이터 타입"
excerpt: "Front의 기초 JS![데이터 타입]"

categories:
    - JavaScript
tags:
    - [JavaScript, Front]
# MarkDown 문법에서 목차를 우측에 보여줄지를 결정
toc: true
# 목차부분이 마우스 스크롤시 고정으로 따라오게 할지를 결정
toc_sticky: true

date: 2022-04-29
last_modified_at: 2022-04-29
---

<div style="text-align:center; color:#ffffff;">
    <h2>해당 post 는 <span style="font-weight:bold; color:#efefef">모던 자바스크립트 Deep Dive</span> 책에 있는 내용을 인용한 post 입니다.</h2>
    <div style="color:eeeeee;">
        <p>모던 자바스크립트 Deep Dive / 위키북스</p>
        <p>이웅모 지음</p>
    </div>
</div>

## 숫자 타입
- C나 JAVA의 경우 정수(소수점 이하가 없는 숫자), 실수(소수점 이하가 있는 숫자)가 구분되어서   
 int, long, float, double 등과 같이 다양한 숫자 타입을 제공합니다.   
하지만 JavaScript의 경우 독특하게 하나의 숫자타입만 존재합니다.
ECMAScript 사양에 따르면 숫자 타입의 값은 배정밀도 64비트 부동소수점 형식을 따릅니다.    
즉 모든 수를 실수로 처리하며, 정수만 표현하기 위한 데이터 타입이 별도로 존재하지 않습니다.
```javascript
    var integer = 10;   // 정수
    var double = 10.12; // 실수
    var negative = -20; // 음의 정수
```
- JavaScript는 2진수, 8진수, 16진수를 표현하기 위한 데이터 타입을 제공하지 않기 때문에   
이들 값을 참조하면 모두 10진수로 해석합니다.

---

- JavaScript의 숫자 타입은 정수만을 위한 타입이 없고 모든 수를 실수로 처리하는데 이는 정수로 표시된다 해도 사실은 실수라는 것을 의미합니다.   
따라서 정수로 표시되는 수끼리 나누더라도 실수가 나올 수 있습니다.
```javascript
    var binart = 0b01000001;    // 2진수
    var octal = 0o101;          // 8진수
    var hex = 0x41;             // 16진수

    // 위의 코드들은 표기법만 다를 뿐 모두 같은 숫자이다.
    console.log(binart);
    // 65;
    console.log(octal);
    // 65;
    console.log(hex);
    // 65;
    console.log(binary === octal);
    // true
    console.log(octal === hex);
    // true

    console.log(1 === 1.0);
    // true
    console.log(4 / 2);
    // 2
    console.log(3 / 2);
    // 1.5
```

- 또한 javaScript의 숫자 타입은 추가적으로 세 가지 특별한 값도 표현할 수 있습니다.
    - Infinity : 양의 무한대
    - -Infinity : 음의 무한대
    - NaN : 산술 연산 불가 (not-a-number)


```javascript
    // 숫자타입의 특별한 세 가지 값
    console.log(10 / 0);
    // Infinity
    console.log(10 / -0);
    // -infinity
    console.log(1 * 'String');
    // NaN
```

- 이 때 주의해야 할 점으로는 JavaScript는 대·소문자를 구별하므로 **NaN** 을 NAN, Nan, nan 등과 같이 표현하면 Error를 출력하게됩니다.    
JavaScript 엔진은 NAN, Nan, nan 을 값이 아닌 식별자로 해석합니다.




## 문자열 타입
- 문자열(String) 타입은 다른 언어와 마찬가지로 텍스트 데이터를 나타내는 데 사용됩니다.    
문자열은 0개 이상의 16비트 유니코드 문자(UTF-16)의 집합으로 전 세계 대부분의 문자를 표현할 수 있습니다.
문자열을 사용할 때는 작은따옴표('') 혹은 큰따옴표("") 또는 백틱(``) 으로 텍스트를 감싸주게 됩니다.   
JavaScript에서 가장 일반적인 표기법은 작은따옴표를 사용하는 것 입니다.

- 문자열 내에서는 줄바꿈이 허용되지 않아서 아래의 표에 있는 이스케이프 시퀸스를 사용해서 줄바꿈 처리를 해줘야 합니다.

|이스케이프 시퀀스|의미|
|---|-----|
|\0|null|
|\b|백스페이스|
|\f|폼 피드(Form Feed) : 프린터로 출력 할 경우 다음 페이지의 시작 지점으로 이동한다.|
|\n|개행(LF, Line Feed) : 다음 행으로 이동한다.|
|\r|개행(CR, Crriage Return) : 커서를 처음으로 이동한다.|
|\t|탭 (수평)|
|\v|탭 (수직)|
|\uXXXX|유니코드, 예를들어 '\u0041'은 'A', '\uD55C'는 '한', '\u{1F600}'은 😁 이다.|
|\'|작은따옴표|
|\"|큰따옴표|
|\\|백슬래시|



## 템플릿 리터럴
- ES6부터 템플릿 리터럴(Template literal)이라고 하는 새로운 문자열 표기법이 도입되었는데   
이 템플릿 리터럴은 멀티라인 문자열, 표현식 삽입, 태그트 템플릿 등 편리한 문자열 처리 기능을 제공합니다.   
템플릿 리터럴은 일반 문자열과 다르게 작은따옴표('')와 큰 따옴표("") 같은 일반적인 따옴표 대신 백틱(``) 을 사용합니다.



## 불리언(boolean) 타입
- 불리언 타입의 값은 논리적 참(true), 거짓(false) 을 나타내기만 합니다.   
추후에 불리언 타입을 이용하여 프로그램의 흐름을 제어하는 조건문에서 자주 사용됩니다.

```javascript
    var foo = true;
    console.log(foo);
    // true

    foo = false;
    console.log(foo);
    //false
```



## undefined 타입
- undefined 타입의 값은 indefined 가 유일합니다. var 키워드로 선언한 변수는 암묵적으로 undefined로 초기화됩니다.   
즉 변수 선언에 의해 확보된 메모리 공간을 처음 할당이 이루어 질 때까지 빈 상태(대부분 비어 있지 않고 쓰레기 값이 들어있다.)로 내버려두지 않고 Javascript 엔진이 undefined로 초기화 시킵니다.    
따라서 변수를 선언한 이후 값을 할당하지 않은 변수를 참조하면 undefined가 반환됩니다.



## null 타입
- null 타입의 값은 null 이 유일합니다. null 또한 대·소문자를 구분하기 때문에 **Null, NULL** 등과 다릅니다.   
변수에 null 을 할당하는 것은 변수가 이전에 참조하던 값을 더이상 참조하지 않겠다는 뜻이며,   
이는 이전에 할당되어 있던 값에 대한 참조를 명시적으로 제거하는 것을 의미합니다.

```javascript
    var foo = 'Kim';

    foo = null;
```

- 만약 함수가 유요한 값을 반환할 수 없는 경우에도 JavaScript는 명시적으로 null 을 반환하기도 합니다.


## 심벌(Symbol) 타입
- 심벌 타입은 ES6에서 추가된 7번째 타입으로 변경이 불가능한 원시 타입의 값 입니다.   
심벌 타입은 다른 값과 중복되지 않는 유일무이한 값이기 때문에 주로 이름이 충돌할 위험이 없는 객체의 유일한 프로퍼티 키를 만들기 위해 사용됩니다.    
심벌 이외의 원시 값은 리터럴을 통해 생성하지만 심벌은 **Symbol** 함수를 호출해 생성합니다.    
이 때 생성된 심벌의 값은 외부에 노출되지 않으며, 다른 값과 절대 중복되지 않는 유일무이한 값 입니다.

```javascript
    let x = 'outer x';
    {
        let x = 'inner x';                                                                             
        let y = 'inner y';                                                                          
        console.log(x);     // inner x                                                              
        console.log(y);     // inner y                                                                
    }
    console.log(x);         // outer x
    console.log(y);         // y is not defined;

```
