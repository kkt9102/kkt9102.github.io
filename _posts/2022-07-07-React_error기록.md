---
title: "[React] 에러 : A component is changing an uncontrolled input to be controlled. This is likely caused by the value changing from undefined to a defined value, which should not happen. Decide between using a controlled or uncontrolled input element for the lifetime of the component"
excerpt: "React Error!"

categories:
  -
tags:
  - [React]
# MarkDown 문법에서 목차를 우측에 보여줄지를 결정
toc: true
# 목차부분이 마우스 스크롤시 고정으로 따라오게 할지를 결정
toc_sticky: true

date: 2022-07-07
last_modified_at: 2022-07-07
---

## console error log

- **react_devtools_backend.js:4026 Warning: A component is changing an uncontrolled input to be controlled. This is likely caused by the value changing from undefined to a defined value, which should not happen. Decide between using a controlled or uncontrolled input element for the lifetime of the component**  
  영어실력이 부족해서 구글번역을 돌려보면 **react_devtools_backend.js:4026 경고: 구성 요소가 제어되지 않는 입력을 제어하도록 변경하고 있습니다. 이는 값이 정의되지 않은 값에서 정의된 값으로 변경되기 때문에 발생할 수 있으며, 이는 발생해서는 안 됩니다. 구성 요소의 수명 동안 제어 또는 제어되지 않은 입력 요소를 사용할지 결정** 이렇게 나옵니다!

- 에러가 발생한 경우는 값의 변경이 제대로 되지 않았을 때 나오는 경우입니다.  
  해당 에러가 발생한 경우는 DTO나 state가 null 일 때 나타납니다. 오류의 해결 방법은 간단합니다.

```javascript
  // 변경 전
  <input value={dto.name}/>

  // 변경 후
  <input value={dto.name || ''}>
```

[!참조 블로그:Jaybon 의 지식창고](https://ondolroom.tistory.com/862){:\_target="\_blank"}
