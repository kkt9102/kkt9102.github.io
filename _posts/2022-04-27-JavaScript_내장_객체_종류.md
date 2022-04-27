---
title: "[JavaScript]내장 객체 종류"
excerpt: "Front의 기초 JS!"

categories:
    - JavaScript
tags:
    - [JavaScript, Front]
# MarkDown 문법에서 목차를 우측에 보여줄지를 결정
toc: true
# 목차부분이 마우스 스크롤시 고정으로 따라오게 할지를 결정
toc_sticky: true

date: 2022-04-27
last_modified_at: 2022-04-27
---

## JavaScrip 내장 객체란
- JavaScript 내장 객체란 처음부터 사용할 수 있는 빌트인 오브젝트를 말합니다. 이 내장 객체는 JavaScript라는 프로그래밍 언어의 뼈대를 구성합니다.

## JavaScript 내장 객체 종류 (ES5 기준)
- 다음의 표는 ES5 기준의 내장 생성자 종류입니다.


<div style="width:100%;">
<table class="table_type_1">
    <colgroup>
        <col width="20%">
        <col width="80%">
    </colgroup>
    <thead>
        <tr>
            <th>생성자 이름</th>
            <th>생성되는 객체</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Object</td>
            <td>일반 객체</td>
        </tr>
        <tr>
            <td>String</td>
            <td>문자열 객체</td>
        </tr>
        <tr>
            <td>Number</td>
            <td>숫자 객체</td>
        </tr>
        <tr>
            <td>Boolean</td>
            <td>논리값 객체</td>
        </tr>
        <tr>
            <td>Array</td>
            <td>배열</td>
        </tr>
        <tr>
            <td>Date</td>
            <td>날짜와 시간을 다루는 객체</td>
        </tr>
        <tr>
            <td>function</td>
            <td>함수 객체</td>
        </tr>
        <tr>
            <td>RegExp</td>
            <td>정규 표현식 객체</td>
        </tr>
        <tr>
            <td>Error</td>
            <td>오류 객체</td>
        </tr>
        <tr>
            <td>EvalError</td>
            <td>eval() 함수와 관련된 오류룰 표현하는 객체</td>
        </tr>
        <tr>
            <td>InternalError</td>
            <td>JavScript 내부에서 발생한 오류릏 표현하는 객체</td>
        </tr>
        <tr>
            <td>RangeError</td>
            <td>값이 허용 범위를 넘었을 때 발생한 오류를 표현하는 객체</td>
        </tr>
        <tr>
            <td>RefercError</td>
            <td>없는 변수를 참조할 때 발생한 오류를 표현한 객체</td>
        </tr>
        <tr>
            <td>SyntaxError</td>
            <td>문법이 어긋날 때 발생한오류를 표현하는 객체/td>
        <tr>
            <td>TypeError</td>
            <td>값이 기대한 타입이 아닐 떄 발생한 오류를 표현하는 객체</td>
        </tr>
        <tr>
            <td>URIError</td>
            <td>잘못된 URI를 만났을 때 발생한 오류를 표현하는 객체</td>
        </tr>
    </tbody>
</table>
</div>

## ES6부터 추가된 내장 생성자 목록 (ES6 기준)
- 아래의 표들은 ES6부터 추가된 내장 생성자 목록입니다.


<div style="width:100%;">
<table class="table_type_1">
    <colgroup>
        <col width="25%">
        <col width="75%">
    </colgroup>
    <thead>
        <tr>
            <th>생성자 이름</th>
            <th>생성되는 객체</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Symbol</td>
            <td>심볼을 생성</td>
        </tr>
        <tr>
            <td>Int8Array8</td>
            <td>부호가 있는 8비트 정수 배열을 생성</td>
        </tr>
        <tr>
            <td>Uint8Array8</td>
            <td>부호가 없는 8비트 정수 배열을 생성</td>
        </tr>
        <tr>
            <td>Int16Array16</td>
            <td>부호가 있는 16비트 정수 배열을 생성</td>
        </tr>
        <tr>
            <td>Uint16Array16</td>
            <td>부호가 없는 16비트 정수 배열을 생성</td>
        </tr>
        <tr>
            <td>Int32Array32</td>
            <td>부호가 있는 32비트 정수 배열을 생성</td>
        </tr>
        <tr>
            <td>Uint32Array32</td>
            <td>부호가 없는 32비트 정수 배열을 생성</td>
        </tr>
        <tr>
            <td>Float32Array32</td>
            <td>32비트 부동소수점 배열을 생성</td>
        </tr>
        <tr>
            <td>Float64Array64</td>
            <td>64비트 부동소수점 배열을 생성</td>
        </tr>
        <tr>
            <td>ArrayBuffer</td>
            <td>고정 길이 이진 데이터 버퍼를 생성</td>
        </tr>
        <tr>
            <td>Promise</td>
            <td>처리 지연 및 비동기 처리를 관리하는 수단을 제공</td>
        </tr>
        <tr>
            <td>Generator</td>
            <td>제너레이터 함수를 다룰 수 있는 수단을 제공</td>
        </tr>
        <tr>
            <td>GeneratorFunction</td>
            <td>제너레이터 함수를 생성</td>
        </tr>
        <tr>
            <td>Proxy</td>
            <td>객체의 기본적인 동작을 재정의하는 기능을 제공</td>
        <tr>
            <td>Map</td>
            <td>key/value 맵을 생성</td>
        </tr>
        <tr>
            <td>Set</td>
            <td>중복을 허용하지 않는 데이터 집합을 생성</td>
        </tr>
        <tr>
            <td>WeakMap</td>
            <td>약한 참조를 유지하는 key/value 맵을 생성</td>
        </tr>
        <tr>
            <td>WeakSet</td>
            <td>약한 참조를 유지하는 고유한 데이터 집합을 생성</td>
        </tr>
    </tbody>
</table>
</div>

## 기타 내장 객체
- 기타 내장 객체는 내장 생성자가 생성하지는 않지만 기본적으로 사용할 수 있는 내장 객체 목록입니다.


<div style="width:100%;">
<table class="table_type_1">
    <colgroup>
        <col width="20%">
        <col width="80%">
    </colgroup>
    <thead>
        <tr>
            <th>내장 객체</th>
            <th>설명</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>전역 객체</td>
            <td>프로그램 어디에서나 사용할 수 있는 객체</td>
        </tr>
        <tr>
            <td>JSON</td>
            <td>JSON을 처리할 수 있는 기능을 제공</td>
        </tr>
        <tr>
            <td>Math</td>
            <td>수학적인 함수와 상수를 제공</td>
        </tr>
        <tr>
            <td>Reflect</td>
            <td>프로그램의 흐름을 가로채는 기능을 제공</td>
        </tr>
    </tbody>
</table>
</div>
