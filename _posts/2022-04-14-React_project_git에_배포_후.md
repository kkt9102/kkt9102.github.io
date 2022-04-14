---
title: "[React]React 프로젝트 git에 배포  시 Link _blank"
excerpt: "React 내 react-router-dom 으로 Link 새창"

categories:
    - React
tags:
    - [React, Github]
# MarkDown 문법에서 목차를 우측에 보여줄지를 결정
toc: true
# 목차부분이 마우스 스크롤시 고정으로 따라오게 할지를 결정
toc_sticky: true

date: 2022-04-14
last_modified_at: 2022-04-14
---

## React Project 배포 시 react-router-dom
- React로 포트폴리오를 만들고 git에 배포할 때 **react-router-dom** 을 사용했을 경우 배포 전 처리할 부분이 아주 약간(?)있었습니다. react-router-dom 내의 기능인 **Link** 를 통하여 해당 프로젝트의 화면 이동을 구현했다면 **BrowserRouter** 에 **basename={process.env.PUBLIC_URL}** 을 추가해야 배포 후 화면이동이 정상적으로 이루어지는 것을 구글링을 통해 알아냈습니다.   
혼자서 무턱대고 프로젝트를 진행했다보니 원리도 제대로 파익을 못한 상태로 진행해서 이 부분에 대해서도 상당한 삽질(?)을 거쳐 알아냈습니다...
```javascript
    <BrowserRouter basename={process.env.PUBLIC_URL}>
        <Routes>
          <Route path="/" element={<Main/>}/>
          <Route path="/Sub" element={<Sub/>}/>
        </Routes>
      </BrowserRouter>
```
- 대충 위의 코드처럼 **Route** 에 path가 **Link** 와 일치하는 경우 element 에 설정되어있는 컴포넌트를 보여주며 **Route** 는 **Routes** 가 감싸주고 있으며 가장 최상위에는 **BrowserRouter** 가 감싸주고 있습니다. 구글링을 했을 때 react-router-dom v5 기준으로 된 글들이 많았는데 최근에 v6으로 업데이트 되면서 react-router-dom 내에 많은것들이 바뀐것을 확인할 수 있었습니다.   
업데이트 후 변경점은 아래의 다른분의 블로그를 통해 자세히 알 수 있습니다!

[참조 블로그 : soryeongk.log](https://velog.io/@soryeongk/ReactRouterDomV6#0-react-v168){:target="_blank"}

- 제가 가장 먼저 확인 한 부분은 **BrowserRouter** 의 사용법이 바뀐 부분이었는데 v5 에서 사용법은 **BrowserRouter** 안애 **Switch** 사용한 점 입니다.

```javascript
    // V5 사용법
    <BrowserRouter>
        <Switch>
            <Route path="/" component={() => <Home/>}/>
            <Route exact path="/Sub" component={() => <Sub/>}/>
        </Switch>
    </BrowserRouter>


    // V6 사용법
    <BrowserRouter>
        <Routes>
            <Route path="/" element={<Main/>}/>
            <Route path="/Sub" element={<Sub/>}/>
        </Routes>
    </BrowserRouter>
```

- 위의 코드를 보면 먼저 Routes 대신 Switch 를 사용하고 있으며 중첩라우팅을 방지하기 위해 exact 를 추가해준 것을 확인할 수 있습니다.   
그리고 컴포넌트 전달방식도 화살표함수를 통하여 해당 컴포넌트를 보여준 모습입니다. 일단... 전 중첩라우팅까진 진행을 못해봐서 중첩라우팅부분은 나중에 알아보겠습니다...   
일단 위의 코드로 작성을 하면 local에서는 화면전환이 정상적으로 이뤄지는 것을 확인할 수 있습니다. 하지만 해당 프로젝트를 git에 배포했을 땐 처음부터 화면이 뜨지않는 처참한 모습을 볼 수 있습니다.   
이 때 정상적으로 배포한 프로젝트를 작동시키기 위해 **basename={process.env.PUBLIC_URL}** 를 추가해주게 됩니다.   


## Link to???
- 일반적으로 html이나 php, jsp에서는 **a** 를 통해 해당 링크로 이동을 하게 되는데 React에는 react-router-dom 내의 Link 를 통하여 해당 컴포넌트를 보여주게 됩니다.    
그래서 코드를 작성할 때 Link 로 작성을 한 후 프로젝트를 실행하게 되면 자동으로 a 로 바뀌는 모습을 확인할 수 있습니다.   
물론 일반적으로 외부 링크나 홈페이지로 이동하는 경우 동일하게 a 엘리먼트를 사용하시면 됩니다.   
포트폴리오 제작 시 초반에 작업을 하려던 방식은 하나의 React 프로젝트 내에서 여러개의 react render를 사용하려 했었습니다. 하지만 해당 방식을 사용하기에는 제 스스로 기초지식이 부족하다고 느껴졌고 실제로도 그러했기 때문에.... 그냥 프로젝트 2개를 사용하게 됬습니다.  
근데 문득 그런생각이 들었습니다. 'Link를 사용하면 새창열기는 안되는건가...?' 근데 됩니다. 매우 간단했습니다...
**<Link to="/" target="_blank">** 입니다. 구글링을 했을때 저게 옳은 방법이 아니라 없는건지 너무 기초적이라 없는건지는 모르겠지만...   
혼자 공부할 때 너무 어렵게 생각해서인지... 무튼 저 방법을 사용하면 프로젝트 내 컴포넌트를 새창으로 불러올 수 있었습니다.
```javascript
    // 컴포넌트 새 창(탭) 열기
    <Link to="/" target="_blank">
``` 


## 배포 후 새창열기가 404를 뿜어낸다!
- 프로젝트 세팅 후 local에서 컴포넌트 새 창 불러오기와 외부페이지 링크가 잘 작동하는 것을 확인한 후 배포를 진행했습니다.   
결과는 매우 잘 됬고 외부페이지도 잘 넘어가는 것을 확인했습니다. 다만 여기서 제가 상당히 큰 부분을 놓치고 있었는데 한 프로젝트 내에서 새 창으로 컴포넌트를 불러오는 부분이었습니다.
![포트폴리오 프로젝트 구성](https://cdn.jsdelivr.net/gh/kkt9102/blog_img/20220414_posts/img1.png)

- 제 포트폴리오는 위의 이미지와 같은 구성이었습니다. 이때 제가 확인하지 못한 게 바로 한 프로젝트 내에서 새 탭으로 컴포넌트 불러오기였습니다. 당연하게도 화면전환이 되니까 새 탭으로 이동도 잘 될꺼라 생각하고 나중에서야 새 탭 컴포넌트 랜더링이 안된다는 것을 확인했습니다.    
뭐가 문제이기에 새 탭 컴포넌트 랜더가 안될까 삽질을 하다가 결국은 도움을 받아 해결하게 됬습니다... 방법은 **BrowserRouter** 대신 **HashRouter** 를 사용하면 배포 후에도 정상적으로 새 창에서 컴포넌트 랜더링이 동작하게 됩니다. 혹시라도 저와같은 문제를 겪고있는 분을 위해 포스팅을.. ㅠㅠㅠ

## 결론은?
- React Project를 github에 배포 후 Page를 사용할 때 한 프로젝트 내에서 새 탭 컴포넌트 랜더링을 하기 위해선 **BrowserRouter** 대신 **HashRouter** 를 사용한다!
