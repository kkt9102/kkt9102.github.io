---
title: "React-Router v6 간단 사용법 "
excerpt: "React 삽질하기"

categories:
    - React
tags:
    - [React, React-Router]
# MarkDown 문법에서 목차를 우측에 보여줄지를 결정
toc: true
# 목차부분이 마우스 스크롤시 고정으로 따라오게 할지를 결정
toc_sticky: true

date: 2022-01-03
last_modified_at: 2022-01-03
---

# 내가 일단 안까먹고 기억해야 사용하니까 기록...
- 무턱대고 React 해보겠다고 책은 샀는데... 책은 잘 안보게되고 멘땅에 헤딩하는 수준으로 무작정 React로 포트폴리오 만들고는 있는데... 이놈이 페이지 이동구현부터 힘들게하는구나...
현재 구글링을해보면 거의 다 React-Router v5 기준으로 설명이 되 있는듯 하다. Switch 로 설명하는 곳도 있기때문에 구글링을 하기전에 꼭 공식문서부터 읽어보는 것을 추천한다.

# React-Router 기본 사용법
- 구글링을 해보면 이 블로그보다 훨씬 더 쉽게 설명해주는 분들이 많습니다...(제가 쓴 글 봐도 제가 말인지 방구인지 못알아먹겠습니다. 제가 100% 이해를 하고 있어야 남들에게 알려주는데...)
- 먼저 React-Router 를 사용하기 위해선 해당 React 프로젝트에 React_Router-Dom 을 설치해주어야 합니다. 저는 현재 윈도우 11 을 사용중이므로 제 기준으로 작성하겠습니다...

- npm 을 이용한 설치
```console
npm install react-router-dom
```
 - yarm 을 이용한 설치
```console
yarn add react-router-dom
```

- 해당 명령어를 이용하면 기본적인 React-Router_Dom 설치가 끝납니다. 
