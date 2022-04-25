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

date: 2022-04-25
last_modified_at: 2022-04-25
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
- 문자열(String) 타입은 다른 언어와 마찬가지로 텍스트 데이터를 나타내는 데 사용됩니다. 문자열은 0개 이상의 16비트 유니코드 문자(UTF-16)의 집합으로 전 세계 대부분의 문자를 표현할 수 있습니다.
문자열을 사용할 때는 작은따옴표('') 혹은 큰따옴표("") 또는 백틱(``) 으로 텍스트를 감싸주게 됩니다.   
JavaScript에서 가장 일반적인 표기법은 작은따옴표를 사용하는 것 입니다.