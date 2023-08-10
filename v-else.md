# 😀 상세페이지와 v-else

전에 만들어둔 모달창안에 상세페이지를 만들어 보자.

근데 이제.. 상품을 클릭하면 해당상품 상세페이지가 뜨도록 만들어 본다..



### 01. data 생성

그러기 위해서 먼저 사용자가 몇번째 상품을 눌렀는지 기록하는 data 생성한다.

```javascript
 data(){
    return{
      clickPrd : 0, //사용자가 몇번째 상품을 눌렀는지 기록하는 daat 생성
    }
  }
```



### 02. 변수 받아오기

```markup
  <div v-for="(a,i) in 원룸들" :key="(a,i)">
    <img :src="a.image" class="room-img">
    <h4 @click="openMd = true; clickPrd = i" class="title"> {{a.title}} </h4>
    <p>{{a.price}} 원</p>
  </div>
```

i는 각 인덱스 번호를 가져와 주기 때문에 clickPrd 를 i로 바뀌게 설정해주면

상품을 눌렀을때 잘 각 상품이 잘 나타나게 된다.



```markup
<div class="black-bg" v-if="openMd == true" >
    <div class="white-bg">
      <h4>{{원룸들[clickPrd].title}}</h4>
      <img :src="원룸들[clickPrd].image">
      <p>{{ 원룸들[clickPrd].content }}</p>
      <p>{{ 원룸들[clickPrd].price }} 원</p>

      <button @click="openMd = false">닫기</button>
    </div>
  </div>
```







### 🙂 v-else 문법

v-if="" 는 조건식이 참일 경우에만 특정 HTML을 보여줄 수 있다.

v-else ="" 위의 v-if가 거짓일때 HTML을 보여준다.



```html
<div v-if="1 == 2">
  안녕하세요
</div>
<div v-else>
  안녕하세요2
</div>
<!-- IF가 거짓이므로 안녕하세요2가 보여짐 -->
```



```html
<div v-if="1 == 2">
  안녕하세요
</div>
<div v-else-if="1 == 3">
  안녕하세요2
</div>
```

이것도 위의 식을 검사해주고 밑에 있는 식을 검사해준다.
