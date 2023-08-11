# 👩💻 Component

html이 복잡해 질거 같으면  component로 축약해서 사용할 수 있다.

**원하는 HTML 덩어리를 한 글자로 축약**할 수 있게 도와주는 문법이 컴포넌트 라고 한다.



### 🙂컴포넌트 쓰는 이유?

1. HTML 쓰다 보면 div 수십개 나오는데 깔끔하게 보이려고 사용한다.
2. 다른 위치에서 같은 HTML 재사용이 쉬워진다.
3. 나중에 라우터 페이지 구분하고 싶으면 하나의 페이지는 하나의 컴포넌트로 만드는게 좋다.





### 🙂 할인배너 만들기

아래와 같은 할인배너HTML 을 컴포넌트 화 시켜보자

```markup
<div class="discount">
  <h4>지금 결제하면 20% 할인</h4>
</div>
```



1. 먼저 컴포넌트 vue파일을 새로 만든다.(<mark style="color:red;">두 단어 이상을 안하면 에러남</mark>)
2. 만든 vue파일을 import 한다.
3. components 에 등록한다.
4. <작명한이름/> 혹은 <작명한이름><작명한이름/> 으로 원하는 부분에 가져다 쓴다.



#### 01.  컴포넌트 파일 만들기

```markup
(DiscountBanner.vue)

<template>
    <div class="discount">
        <h4>지금 결제하면 20% 할인</h4>
    </div>
</template>

<script>
    export default {
        name: 'DiscountBanner',
        //name : '작명' 의 형태로 작성 (디버깅할때 쓰인다)
    }
</script>

<style>

</style>

```



#### 02, 03 import + 등록하기

```javascript
(App.vue)

<script>
import DiscountBanner from './DiscountBanner.vue';
// DiscountBanner.vue 파일 import 하기

export default {
  data(){
  },
  components: {
    DiscountBanner : DiscountBanner,
    // components 에 `작명 : DiscountBanner` 으로 등록한다.
}
}
</script>

```

작명은 자유롭게 가능하지만 일반적으로 똑같이 하는게 보통이다.



#### 04. 원하는 html에 가져다 쓰기

```markup
(App.vue)

<DiscountBanner/>  

```

