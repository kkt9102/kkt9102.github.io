---
title: "[React, kakaoAPI] React에서 카카오맵 사용기"
excerpt: "React는 어렵다"

categories:
    - React, API
tags:
    - [React, API, JavaScript]
# MarkDown 문법에서 목차를 우측에 보여줄지를 결정
toc: true
# 목차부분이 마우스 스크롤시 고정으로 따라오게 할지를 결정
toc_sticky: true

date: 2022-04-02
last_modified_at: 2022-04-02
---

# 왜 카카오맵 API인가?
- 웹 앱중에 지도 API를 지원해주는곳은 크게 구글, 네이버, 카카오, 국토교통부 등이 있는걸로 기억하고 있습니다. 사람들에게 가장 익숙한게 네이버일테니 네이커 지도 API를 사용했을법도 한데... 사실 제가 그냥 카카오맵 쓰고 구글링 찾아서 가장 먼저 나온게 카카오맵 API라서 카카오 맵 API를 사용하게 됬습니다...

![카카오 개발자홈페이지 메인](https://cdn.jsdelivr.net/gh/kkt9102/blog_img/20211215_posts/img(0).png)
카카오 개발자홈페이지 메인

<div class="link_b">
    <a href="https://developers.kakao.com/" target="_blank">카카오 개발자홈페이지 바로가기</a>
</div>

- 카카오맵 API사용법은 이전 포스팅에서도 간단하게 설명했고 사실 구글링하면 저보다 더 자세하고 이해하기 쉽게 포스팅해놓으신 분들이 많습니다...!!!

![카카오 맵 가이드 메인](https://cdn.jsdelivr.net/gh/kkt9102/blog_img/20220331_posts/img1.png)
카카오 맵 가이드 메인

<div class="link_b">
    <a href="https://apis.map.kakao.com/" target="_blank">카카오 맵 가이드 바로가기</a>
</div>

- 사실 포트폴리오에 카카오맵 API를 사용하면서 카카오맵 관련 구글링만하다보니 다른 API들의 설명과 샘플은 어떤지 구경을 못해본 상태입니다만.. 카카오의 경우 위의 카카오맵 가이드용 홈페이지에 샘플코드들이 생각보다 다양하게 있어서 작업을 진행하는데는 크게 문제는 없었습니다..

# 근데 React에 카카오맵은 왜...?
- 이번에 이직을 하게 되면서 포트폴리오를 살짝 갈아엎으면서... 서버를 대여하기에는 부담스럽고 AWS 처음사용 시 한달 무료를 벌써 쓰기에는 AWS 공부를 한 적도 없고 해서 github의 page를 이용하기로 했습니다.  
근데 왜 React로 만들었냐...?? 현재 제가 가고싶은 포지션은 퍼블리셔 -> 프론트로 넘어가는 중인데 프론트라면 역시 요즘 핫한 언어를 사용해보는게 좋을 거 같다 생각해서 React로 진행하게 됬습니다. 진짜 기초지식 1도 없이 무작정 맨땅에 헤딩하는 심정으로 React를 사용하여 진행했는데요... jsp나 html에서 간단하게 진행하던 것들도 하나하나 고난의 연속이긴 했습니다.   

- 서론이 너무 긴거같으니 바로 제가 진행한 소스들을 기록해보겠습니다!

# 일반적인 jps나 html과 사용하는방법이 다른건가...?
- 사용법은 거의 비슷하긴 합니다... 아마 어렵게 느껴지는 이유는 제가 공부안하고 일단 무작정 시작해서 그런거라 생각됩니다. ㅠㅠ   
포트폴리오를 만들면서 카카오맵 API 자료를 찾다보니 이미 감사하게도 누군가가 React용 카카오맵 API 모듈을 만들어놓으셨더라고요. 하지만 저걸 발견했을 때는 다시 삽질을 해야하는 상황이라 그냥 기존 카카오맵 소스를 활용하기로 했습니다. 해당 페이지 주소는 아래에 있습니다!

<div class="link_b">
    <a href="https://react-kakao-maps-sdk.jaeseokim.dev/" target="_blank">React용 카카오맵 모듈</a>
</div>

# 일단 DB를 사용하지 않고 MapMarker 룰 배열로 뿌려주기
- 먼저 카카오맵에 원하는 곳에 마커를 표시해주려면 그 좌표의 정확한 위도와 경도를 알아야 했습니다.

![카카오 맵 가이드 메인](https://cdn.jsdelivr.net/gh/kkt9102/blog_img/20220331_posts/img2.png)
직접 작성한 코드 화면

- 스타벅스를 좀 많이 좋아하다보니 스타벅스 리디자인을 진행할 때 각 매장들의 위치에 마커를 찍기위해 위도와 경도를 기록해줘야했는데 실제 사용되는 홈페이지는 매장들의 정보를 DB에 보관하며 관리했을 듯 합니다... 하지만 전 개인 NAS도 없고 서버를 대여해서 세팅을 해보며 삽질 할 시간이 충분하지 않아서 위의 사진처럼 매장별 위도와 경도를 다 넣어줬습니다. 카카오맵 API홈페이지에는 다양한 샘플과 그에 해당하는 코드들도 자세하게 설명이 되어있으니 꼭 참고해주세요. 아래 코드는 공식 가이드에서 가져온 코드입니다.
```javascript
var mapContainer = document.getElementById('map'), // 지도를 표시할 div  
    mapOption = { 
        center: new kakao.maps.LatLng(33.450701, 126.570667), // 지도의 중심좌표
        level: 3 // 지도의 확대 레벨
    };

var map = new kakao.maps.Map(mapContainer, mapOption); // 지도를 생성합니다
 
// 마커를 표시할 위치와 title 객체 배열입니다 
var positions = [
    {
        title: '카카오', 
        latlng: new kakao.maps.LatLng(33.450705, 126.570677)
    },
    {
        title: '생태연못', 
        latlng: new kakao.maps.LatLng(33.450936, 126.569477)
    },
    {
        title: '텃밭', 
        latlng: new kakao.maps.LatLng(33.450879, 126.569940)
    },
    {
        title: '근린공원',
        latlng: new kakao.maps.LatLng(33.451393, 126.570738)
    }
];

// 마커 이미지의 이미지 주소입니다
var imageSrc = "https://t1.daumcdn.net/localimg/localimages/07/mapapidoc/markerStar.png"; 
    
for (var i = 0; i < positions.length; i ++) {
    
    // 마커 이미지의 이미지 크기 입니다
    var imageSize = new kakao.maps.Size(24, 35); 
    
    // 마커 이미지를 생성합니다    
    var markerImage = new kakao.maps.MarkerImage(imageSrc, imageSize); 
    
    // 마커를 생성합니다
    var marker = new kakao.maps.Marker({
        map: map, // 마커를 표시할 지도
        position: positions[i].latlng, // 마커를 표시할 위치
        title : positions[i].title, // 마커의 타이틀, 마커에 마우스를 올리면 타이틀이 표시됩니다
        image : markerImage // 마커 이미지 
    });
}
```

- 공식 가이드는 일반적인 JavaScript에서 for문을 활용하여 여러개의 마커를 보여주고 있습니다. 초반에 작업할 때는 가이드북을 그대로 사용하여 지도에 마커를 뿌려주는 부분과 배열 부분을 하나의 JS파일에 작성하다보니 코드의 길이가 너무 길어지는 현상이 있어서 마커의 정보를 담는 JS와 실제 반복문 등 마커와 이벤트를 제어하는 코드를 분리해주기로 했습니다.

```javascript
    // Map_Marker.js
    export const MapMark = [
        // 배열 MapMark에 들어갈 내용들
     {
        content:
        '<div class="store_popup">' +
        '   <div>내용이 주르륵</div>' +
        '</div>',
        // 추후 infowindow나 overlay를 사용할 때 html 방식으로 보여주기위한 코드
        lat: 37.646213, 
        lng: 126.893264
        // 해당 배열이 보여질 위도,경도 정보
    },
```

- 배열작성은 어려울게 없습니다. 단지 노가다성일 뿐입니다... 마커를 보여줄 위도와 경도를 일일이 다 입력했을 뿐입니다.

```javascript
    // KakaoMap.js
    import { MapMark } from "../components/map_mark";
    // 마커의 위도와,경도가 담긴 컴포넌트를 import 시켜주기
    import ReserveMarker from '../resources/img/map_mark.png';
    // 커스텀 마커 이미지 불러오기

    
    .
    .
    .
    MapMark.forEach((reserve) => {
    // 커스텀 마커 반복문 돌려주기(reserve란 이름으로 정보 가져오기)
        const imageSrc = ReserveMarker,
        // 커스텀 마커 이미지 경로
        imageSize = new kakao.maps.Size(27,46);
        // 커스텀 마커  이미지의 사이즈(width,height); px을 붙이지 않으면 자동으로 px로 인식
        const reserveMaker = new kakao.maps.MarkerImage(imageSrc,imageSize);
        // 커스텀 마커의 정보
        const custom_marker = new kakao.maps.Marker({
        map: map,
        position: new kakao.maps.LatLng(reserve.lat, reserve.lng),
        // 커스텀마커의 위도,경도
        image: reserveMaker,
        // 커스텀 마커의 이미지 파일
        });
    .
    .
    .
    }
```
- 공식 가이드와 다른점이라면 일단 for문 대신 forEach 를 사용한 점 입니다. 일단 저는 공부중이라 뭐가 어떻다라고 자세하게 설명은 드릴 자신이 없습니다... 일단은 잘 나옵니다... 혹시라도 댓글로 설명주시는분이 계신다면 정말 감사하겠습니다!
<div class="link_b">
    <a href="https://github.com/kkt9102/starbucksreserve/blob/main/src/utils/kakaoMap.js" target="_blank">작성 코드 보러가기</a>
</div>

- 위의 코드를 보면 먼저 커스텀 마커로 쓸 이미지 파일의 경로를 지정해준 후 마커의 크기 기정, 그 후 실제 보여줄 마커의 기본적인 정보를 변수로 설정한 후 **new kakao.maps.Marker({...})** 를 통하여 마커를 보여주고 있습니다. 카카오맵을 이용하여 간단하게 표현하는부분은 크게 무리없이 잘 되는거 같습니다.

# 마커 클릭이벤트
- 다음으로는 마커를 클릭했을 때 해당 마커에 대한 infowindow를 나타내는 방법입니다. 먼저 공식 가이드에 나와있는 infowindow를 띄우는 샘플코드를 보겠습니다.

```javascript
    var mapContainer = document.getElementById('map'), // 지도를 표시할 div 
        mapOption = { 
            center: new kakao.maps.LatLng(33.450701, 126.570667), // 지도의 중심좌표
            level: 3 // 지도의 확대 레벨
        };

    var map = new kakao.maps.Map(mapContainer, mapOption); // 지도를 생성합니다

    var iwContent = '<div style="padding:5px;">Hello World!</div>', // 인포윈도우에 표출될 내용으로 HTML 문자열이나 document element가 가능합니다
        iwPosition = new kakao.maps.LatLng(33.450701, 126.570667), //인포윈도우 표시 위치입니다
        iwRemoveable = true; // removeable 속성을 ture 로 설정하면 인포윈도우를 닫을 수 있는 x버튼이 표시됩니다

    // 인포윈도우를 생성하고 지도에 표시합니다
    var infowindow = new kakao.maps.InfoWindow({
        map: map, // 인포윈도우가 표시될 지도
        position : iwPosition, 
        content : iwContent,
        removable : iwRemoveable
    });
        
    // 아래 코드는 인포윈도우를 지도에서 제거합니다
    // infowindow.close(); 
``` 

- 위의 코드를 실제로 적용하면 infowindow가 표시된 상태로 맵이 실행됩니다. 하지만 제 목표는 마커를 클릭했을 때 그에 해당하는 마커의 infowindow가 나오는게 목표입니다.

```javascript
    // infowindow에 넣을 컨텐츠
    const iwContent = reserve.content

    // infowindow 정보
    const infowindow = new kakao.maps.InfoWindow({
        content : iwContent,
        // content에 iwContent를 넣어준다
        removable : true,
        // removable:true 로 설정해줌으로써 infowindow를 닫을 수 있는 x버튼이 생성됩니다.
    });

    // 만약 열려있는 infowindow가 열려있을 시 기존의 infowindow를 닫고 클릭한 마커의  infowindow를 열기위한 코드
    infos.push(infowindow);

    var openInfo = function() {
      infos.forEach(function(each) { each.close(); }); // close all infos
      infowindow.open(map, custom_marker); // open target info
  };

    // 마커를 클릭했을 때 infowindow가 열린다.
    kakao.maps.event.addListener(custom_marker, 'click', openInfo);
```
- 위의 코드는 제가 사용한 코드 중 클릭 이벤트와 그에 해당하는 infowindow 가 열리게 하는 부분입니다. 카카오맵  API에서 infowindow와 customOverlay 가 있는데 알아본 결과 infowindow의 경우 간단하게 정보를 표시하는데 용이하며 customOverlay의 경우 infowindow 에 비해 좀 더 다이나믹하게 커스텀이 가능하다고 다른 블로그나 개발자포롬에서 말하고있습니다. 상황에 맞게 사용하면 될 듯 합니다. 일단은 이 글은 다양한 분들에게 사용법을 설명한다기보단 제가 개인적으로 사용하고 까먹지 않기 위해 기억하기위해 적은 글이다보니 상당히 두서없고 목적이 없는 글입니다.... 나중에 제가 정확하게 이해한 후 다양한 커스텀방법과 소스를 올리겠습니다...