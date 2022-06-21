---
title: "[JavaScript]변수에 할당 된 데이터 타입 조회 방법"
excerpt: "Front의 기초 JS!"

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

## JavaScript 데이터 타입 조회 방법
- **typeof** "조회할 변수명"

```javascript
    // 변수에 할당된 값 데이터 타입 체크 방법
    var abc;
    console.log(typeof abc);
    // undefined;

    abc = 10;
    console.log(typeof abc);
    // number;

    abc = 'Hello';
    console.log(typeof abc);
    // string;

    abc = true;
    console.log(typeof abc);
    // boolean;

    abc = null;
    console.log(typeof abc);
    // object;

    abc = Symbol();
    console.log(typeof abc);
    // symbol;

    abc = {};
    console.log(typeof abc);
    // object;

    abc = [];
    console.log(typeof abc);
    // object;

    abc = function () {};
    console.log(typeof abc);
    // function;
```