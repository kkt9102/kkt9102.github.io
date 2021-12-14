---
title: "[slick slider]슬릭슬라이더 사용법 "
excerpt: "Library 사용법"

categories:
    - Library
tags:
    - [HTML, CSS, JavaScript]

toc: true
toc_sticky: true

date: 2021-12-29
last_modified_at: 2021-12-29
---


- 슬라이드 라이브러리중 포트폴리오를 준비해오면서 가장 많이 사용한 플러그인인 'Slick Slider' 사용법을 간단하게 소개하려고 합니다. 분명 슬릭슬라이더는 라이센스 비용이 있던걸로 기억하는데 최근에 다시 확인해봤을때는 프리라이센스로 확인되었다...
먼저 슬릭슬라이더를 사용하기 위해 먼저 아래의 코드를 선언해줍니다.

# 1. 슬릭슬라이더 라이브러리 추가
```html
<!-- 제이쿼리 불러오기 -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.2.4/jquery.min.js"></script>
 
<!-- Slick 불러오기 -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/slick-carousel/1.9.0/slick.min.js"></script>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/slick-carousel/1.9.0/slick.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/slick-carousel/1.9.0/slick-theme.min.css">
```

# 2. 슬라이더를 표현할 html에 코드 추가하기
- 해당 코드를 선언해주면 슬릭슬라이더를 사용하기위한 기초 작업이 끝난다. 그 후 슬라이더를 표현해주고 싶은 부분에 아래 코드를 넣어줍니다.

```html
    <!-- stlye 은 slick 영역 확인용 -->
    <div style="padding:300px 100px; background-color: skyblue;">
          <div id="slider-div"  >
            <div>1</div>
            <div>2</div>
            <div>3</div>
            <div>4</div>
            <div>5</div>
            <div>6</div>
            <div>7</div>
            <div>8</div>
            <div>9</div>
            <div>10</div>
          </div>
    </div>
```

# 3. 슬릭슬라이더 설정 스크립트 넣어주기
- 그 다음 슬릭슬라이더 플러그인 설정값인 아래의 코드를 선언해줍니다.
```javascript
<script>
          $(function(){
            $('#slider-div').slick({
                slide: 'div',        //슬라이드 되어야 할 태그 ex) div, li 
                infinite : true,     //무한 반복 옵션     
                slidesToShow : 4,        // 한 화면에 보여질 컨텐츠 개수
                slidesToScroll : 1,        //스크롤 한번에 움직일 컨텐츠 개수
                speed : 100,     // 다음 버튼 누르고 다음 화면 뜨는데까지 걸리는 시간(ms)
                arrows : true,         // 옆으로 이동하는 화살표 표시 여부
                dots : true,         // 스크롤바 아래 점으로 페이지네이션 여부
                autoplay : true,            // 자동 스크롤 사용 여부
                autoplaySpeed : 10000,         // 자동 스크롤 시 다음으로 넘어가는데 걸리는 시간 (ms)
                pauseOnHover : true,        // 슬라이드 이동    시 마우스 호버하면 슬라이더 멈추게 설정
                vertical : false,        // 세로 방향 슬라이드 옵션
                prevArrow : "<button type='button' class='slick-prev'>Previous</button>",        // 이전 화살표 모양 설정
                nextArrow : "<button type='button' class='slick-next'>Next</button>",        // 다음 화살표 모양 설정
                dotsClass : "slick-dots",     //아래 나오는 페이지네이션(점) css class 지정
                draggable : true,     //드래그 가능 여부 
                
                responsive: [ // 반응형 웹 구현 옵션
                    {  
                        breakpoint: 960, //화면 사이즈 960px
                        settings: {
                            //위에 옵션이 디폴트 , 여기에 추가하면 그걸로 변경
                            slidesToShow:3 
                        } 
                    },
                    { 
                        breakpoint: 768, //화면 사이즈 768px
                        settings: {    
                            //위에 옵션이 디폴트 , 여기에 추가하면 그걸로 변경
                            slidesToShow:2 
                        } 
                    }
                ]
 
            });
          })
    </script>
```

- 아래의 javascript까지 선언을 해준 후 확인을 해보면 슬라이드가 실행된다. 슬릭슬라이더 커스터마이징 방법은 다른 포스팅에서 다루겠습니다.

- HTML 및 JavaScrpt 출처 : [https://programmer93.tistory.com/34](https://programmer93.tistory.com/34)

- 슬릭슬라이더 홈페이지 : [kenwheeler.github.io/slick/](kenwheeler.github.io/slick/)