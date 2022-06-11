---
title: "[React]filter, map, react-router-dom v6 활용기"
excerpt: "분명 더 좋은 방법이 있을꺼야..."

categories:
    - React
tags:
    - [React, JavaScript]
# MarkDown 문법에서 목차를 우측에 보여줄지를 결정
toc: true
# 목차부분이 마우스 스크롤시 고정으로 따라오게 할지를 결정
toc_sticky: true

date: 2022-06-11
last_modified_at: 2022-06-11
---

## filter 그리고 map
- **개인적으로 까먹지 않기 위해 기록한 코드입니다!!! 해당 코드가 무조건 맞는 것은 아닙니다!**    
**분명 제가 작성한 코드보다 더 안전하면서 깔끔한 코드를 작성하신 분이 있을겁니다....**

- 개인적인 포트폴리오를 업그레이드 하는 중 NAS 를 집에 들여놓기엔 초기셋팅비용이 부담스럽고 서버를 대여하자니 현재로썬 그냥 단순하게 업그레이드하는 수준이라   
그냥 DB를 사용하지 않고(?) github Page를 활용하기로 했습니다. React라면 REST API라도 사용해봐야하는데... JSON 대신 배열 컴포넌트를 활용하여   
화면 구성을 진행하고 있습니다...

## 이상하게 꼬인 컴포넌트 구조
- 작성한 컴포넌트와 코드들입니다. 무작정 작성하며 나누다보니 이상하게 꼬인 경향이 있습니다... App.js에 Route를 모두 넣은 후   
Main 에 각 영역들을 담당하는 컴포넌트를 구생했습니다. 그 중 하나의 컴포넌트에 Link를 동하여 서브 페이지로 넘어가는 구조입니다.

- App.js
```javascript
// App.js
    import { Routes, Route } from "react-router-dom";
    import Main from './component/Main';
    import Sub1 from './component/Sub1';
    import Sub2 from './component/Sub2';

    const App = () => {
    return (
        <>
        <HelmetProvider>
            <Routes>
                <Route path="/" element={<Main/>}/>
                <Route path="/sub1/:name" element={<Sub1/>}/>
                <Route path="/sub2/:name" element={<Sub2/>}/>
            </Routes>
        </HelmetProvider>
        </>
    );
    }

    export default App;
```

- Main.js
```javascript
//Main.js
    import Section1 from './section1';
    import Section2 from './section2';

    const Main = () => {
        return (
            <>
                <div>Header영역도 따로 존재하지만 너무 귀찮아서 코드상은 이렇게만 표현...</div>
                <Section1/>
                <Section2/>
            </>
        )
    }

    export default Main;
```

- Section2.js
```javascript
// Section2.js
    import { Link } from 'react-router-dom';

    const Section2 = () => {
        return (
            <>
                <Link to="/Sub1/aaa">링크도 실제로는 배열로 뿌리고있습니다!</Link>
                <Link to="/Sub1/bbb">링크도 실제로는 배열로 뿌리고있습니다!</Link>
            </>
        )
    }

    export default Section2;
```

- Sub1.js
```javascript
    import DummyArray from './DummyArray';

    const Sub1 = () => {
        return (
            <>
                <DummyArray/>
            </>
        )
    }

    export default Sub1;
```

- dummyArray.js
```javascript
// 배열을 가지고 있는 컴포넌트
    import { useParams } from "react-router-dom";

    const DummyArray = () => {
        const DBArray = [
            {
                id:1,
                name:'aaa',
                contents:'아이고맙소사'
            },
            {
                id:2,
                name:'bbb',
                contents:'공부해야지'
            },
        ];

        const name = useParams();
        const dummyinfo = dummy.filter(dummyinfos =>
            dummyinfos.tag === `${name.name}`).map(dummyinfos =>
                <div key={dummyinfos.id}>
                        <div>{dummyinfos.name}</div>
                        <div>{dummyinfos.contents}</div>
                    </div>
            );

            return (
                <>
                    {dummyinfos}
                </>
            )
    }

    export default DummyArray;
```
- 결국은 react-router-dom 의 기본적인 Link를 통해 params를 전달해준 후 **(Section2.js)** 실제 넘어가는 컴포넌트 **(Sub1.js)** 에서 보여줄 때    
filter 를 통해 해당하는 배열을 보여주는 아주 간단한 방법입니다...    
따끔한 지적과 조금 더 간단하고 명확한 해결방안 답변은 감사하겠습니다!!!