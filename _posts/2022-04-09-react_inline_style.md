---
title: "[React] React에서 인라인 스타일링하기"
excerpt: "React 인라인스타일"

categories:
    - React
tags:
    - [React, CSS]
# MarkDown 문법에서 목차를 우측에 보여줄지를 결정
toc: true
# 목차부분이 마우스 스크롤시 고정으로 따라오게 할지를 결정
toc_sticky: true

date: 2022-04-09
last_modified_at: 2022-04-09
---

## React에 인라인 스타일링하기_1

- 첫번째 방법으로 객체형태로 스타일을 작성합니다. 단 주의할 점은 스타일 작성 중 - 이 들어가는 css style 의 경우 카멜 표기법을 활용하여 작성해야 합니다.

```javascript
import React from 'react';

const Test = () => {
    const name = '리액트';
    const style = {
        width: 100,                             // px이나 rem 같이 단위를 붙여주지 않으면 자동으로 px로 인식된다.
        height: 5 + 'rem',                      // px 이외의 다른 단위를 사용하는 방식
        color: 'red',                           // 일반적인 color 이름을 지정하는 방식
        backgroundColor: '#efefef',             // HEX 코드로 작성하는 방식
        border: 10,                             // border 사용 시 border의 두깨
        borderColor: 'rgba(10,10,10,1)',        // border의 color
        borderStyle: 'dotted',                  // border-style
        fontSize: 2 + 'rem',                    
        fontWeight: 600,
    }
    return(
        <>
            <div style={style}>{name} 인라인 스타일 작성하기</div>
        </>
    )
}

export default Test;
```

- 위의 작성법 중 color 의 작성법은 일반적인 css 처럼 3가지 방법이 있는데 첫번째로는 직접 color의 이름을 작성해주는 방법입니다. 'red' 'blue' 등 색의 고유이름이 있을 경우 사용합니다.   
두번째로는 HEX Code를 사용하는 방법인데 일반적인 방법과 다르지 않습니다. '#efefef', '#ff00ff' 등 색의 고유적인 이름보다 조금 더 다양한 색을 사용할 수 있습니다.   
세번째로는 RGB Code 를 사용하는 방법인데 이 방법 또한 작성법이 일반적인 css 작성법과 크게 다르지 않습니다.



## React에 인라인 스타일링하기_2

- React에 인라인스타일링을 하는 두번째 방법은 일반적인 HTML이나 JSP에서 사용하는 **<div style="background-color:#ff00ff;'>Test</div>** 처럼 작성하는 방법입니다.

```javascript
    import React from 'react';

const Test = () => {
    const name = '리액트';
    const 
    return(
        <>
            <div style = {
                width: 100,                             // px이나 rem 같이 단위를 붙여주지 않으면 자동으로 px로 인식된다.
                height: 5 + 'rem',                      // px 이외의 다른 단위를 사용하는 방식
                color: 'red',                           // 일반적인 color 이름을 지정하는 방식
                backgroundColor: '#efefef',             // HEX 코드로 작성하는 방식
                border: 10,                             // border 사용 시 border의 두깨
                borderColor: 'rgba(10,10,10,1)',        // border의 color
                borderStyle: 'dotted',                  // border-style
                fontSize: 2 + 'rem',                    
                fontWeight: 600,
            }
            >{name} 인라인 스타일 작성하기</div>
        </>
    )
}

export default Test;
```

- 두번째 방법도 첫번째 방법과 동일하게 카멜표기법을 사용하여 작성하여야하며 일반적으로 작성하는 인라인 스타일과는 조금 다른 방식으로 작성해야합니다.   
두가지 방법의 차이점은 먼저 선언해준 후 여러군데에 사용하거나 하나의 앨리먼트에만 적용하는지에 따라 사용하면 되겠습니다.