---
title: "[yarn] 자주쓰는 yarn commend 목록"
excerpt: "패키지 설치 모듈인 yarn 알아가기"

categories:
    - React
tags:
    - [React]
# MarkDown 문법에서 목차를 우측에 보여줄지를 결정
toc: true
# 목차부분이 마우스 스크롤시 고정으로 따라오게 할지를 결정
toc_sticky: true

date: 2022-04-20
last_modified_at: 2022-04-20
---

# npm 말고 yarn
- React Project 생성 시 Node.js 를 설치하면 기본적으로 설치되는 패키지 모듈인 npm 을 이용하는 법이 있지만 npm 보다 속도나 기능적인 면, 그리고 보안적인 문제에서도 조금 더 좋은 yarn 을 사용하려 합니다.    
실제 yarn commend 는 npm과 크게 다르지 않아 어렵지는 않습니다.     

- yarn은 yarn.lock이나 package.json으로부터 설치만 하며, yarn.lock은 모든 디바이스에 같은 패키지를 설치하는 것을 보장하기 때문에 버전의 차이로 인해 생기는 버그 방지가 가능합니다.

# yarn package 설치하기
- 따로 파일을 다운받아 설치할 필요가 없습니다.    
먼저 명령 프롬포트를 열거나 VSCode 내의 터미널 창에 아래의 코드를 입력하여     
yarn package 를 설치합니다.
```console
    npm install yarn
```
yarn package 설치는 이러면 끝납니다.

# 대표적으로 쓰이는 commend
- **yarn create react-app project_name** : React Project를 생성    
(npm 을 이용한 create-react-app 과 다른점이라면 creact 다음에 **-** 이 들어가지 않습니다.)
- **yarn init** : package.json 생성
- **yarn or yarn install** : package.json 파일 및 해당 종속성에 나열된 모든 모듈을 설치
- **yarn add package_name@버전** : 특정 패키지의 특정 버전 설치
- **yarn add 주소** : 특정 저장소 내 패키지 설치. 주로 github를 이와 같이 설치
- **yarn global add package_name** : 옵션, global 설치, local의 다른 프로젝트도 이 패키지를 사용 가능하게 됨
- **yarn remove** : 패키지 삭제 명령어
- **yarn upgrade** : 설치한 패키지들의 업데이트 진행
- **npm dedupe** : 중복 설치된 패키지들을 정리


---



[출처 : 천천히 꾸준하게](https://resilient-923.tistory.com/351){:target="_blank"}