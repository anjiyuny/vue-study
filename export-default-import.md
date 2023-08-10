# 😅 export default / import

###

### 🙂 export default / import 문법&#x20;



js 파일에서 만든 변수나 자료를 다른 js파일에서 사용하고 싶은 경우에 export와 import문법을 사용한다.

```javascript
(oneroom.js)
var apple = 10;
export default apple  

// 변수 두개일
(oneroom.js)
var apple = 10;
var apple2 = 100;
export { apple, apple2 }
```

```javascript
(App.vue)
import 작명 from './oneroom.js파일경로'

// 변수두개일때
(App.vue)
import { apple, apple2 } from './oneroom.js파일경로'
```

변수 apple을 내보내기 하고 app.vue에서 가져오는것 정도로 생각하면 될거 같다.

* export default 는 파일 맨 마지막에 한번 사용가능하다.
* import 작명은 자유롭게 가능하다.
* 변수가 여러개 일때는 export 는저런식으로 원하는 만큼 사용할수 있지만
* import시에는 작명이 불가하며 변수명 그대로 작성해야한다.





### 🙂사용해보기



```markup
<div v-for="(a,i) in 원룸들" :key="(a,i)">
    <img :src="원룸들[i].image" class="room-img">
    <h4> {{원룸들[i].title}} </h4>
    <p>{{원룸들[i].price}} 원</p>
</div>
```

````javascript

import data from './assets/oneroom';  // 저장된 data라는 이름의 데이터 가져오기

export default {
  data(){
    return{
      원룸들 : data,   // 원룸들 이라는 이름에 저장
    }
  }
}
```
````

```javascript


export default [{
    id : 0,
    title: "Sinrim station 30 meters away",
    image: "https://codingapple1.github.io/vue/room0.jpg",
    content: "18년 신축공사한 남향 원룸 ☀️, 공기청정기 제공",
    price: 340000
    },
    {
    id : 1,
    title: "Changdong Aurora Bedroom(Queen-size)",
    image: "https://codingapple1.github.io/vue/room1.jpg",
    content: "침실만 따로 있는 공용 셰어하우스입니다. 최대 2인 가능",
    price: 450000
    },
    {
    id : 2,
    title: "Geumsan Apartment Flat",
    image: "https://codingapple1.github.io/vue/room2.jpg",
    content: "금산오거리 역세권 아파트입니다. 애완동물 불가능 ?",
    price: 780000
    },
    {
    id : 3,
    title: "Double styled beds Studio Apt",
    image: "https://codingapple1.github.io/vue/room3.jpg",
    content: "무암동인근 2인용 원룸입니다. 전세 전환가능",
    price: 550000
    },
    {
    id : 4,
    title: "MyeongIl Apartment flat",
    image: "https://codingapple1.github.io/vue/room4.jpg",
    content: "탄천동 아파트 월세, 남향, 역 5분거리, 허위매물아님",
    price: 680000
    },
    {
    id : 5,
    title: "Banziha One Room",
    image: "https://codingapple1.github.io/vue/room5.jpg",
    content: "반지하 원룸입니다. 비올 때 물가끔 새는거 빼면 좋아요",
    price: 370000
  }];
```

위와 같은 형식으로 저장되어있는 데이터 이기 때문에

HTML에서 데이터 바인딩 하기 위해서 <mark style="background-color:red;">**원룸들\[숫자].title**</mark> 의  형식으로 가져와야 한다.
