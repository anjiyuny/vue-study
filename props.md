---
description: 부모가 가진 데이터를 자식이 쓰고 싶으면 props로 전달해준다
---

# 😋 Props

지난번 데이터바인딩으로 만들어둔 모달창을  component화 해서 기능이 작동하도록 하려고한다.

```markup
(Modal.vue)

<template>
    <div class="black-bg" v-if="openMd == true" >
    <div class="white-bg">
      <h4>{{원룸들[clickPrd].title}}</h4>
      <img :src="원룸들[clickPrd].image">
      <p>{{ 원룸들[clickPrd].content }}</p>
      <p>{{ 원룸들[clickPrd].price }} 원</p>

      <!-- <button @click="openMd = false">닫기</button> -->
    </div>
  </div>
</template>

<script>
export default {
    name : "ModalWhite",
}
</script>

<style>

</style>
```

문제는 이렇게 <mark style="color:blue;">데이터바인딩 하려면 data가 같은 파일 안에 있어야 하는데</mark> 없어서 작동하지 않는다는것.

그렇다고 해서 <mark style="color:red;">원룸들 이라는 data를 복붙하면 안된다.</mark>





### 자식이 부모가 가진 데이터 쓰려면 props



컴포넌트에서 데이터바인딩에 쓰인 데이터들을 어케 가져오냐&#x20;

방법은 App.vue에 있던 원룸들이라고 저장해둔 데이터를 전송해서 쓰는 것입니다.

<mark style="color:blue;">하위컴포넌트로 데이터를 전송하려면</mark> <mark style="color:blue;"></mark><mark style="color:blue;">**props**</mark><mark style="color:blue;">라는 문법으로 Modal.vue에 보내면 됩니다.</mark>&#x20;



![](<.gitbook/assets/그룹 1.png>)



1.  이렇게 데이터바인딩 문법으로 데이터를 ModalWhite로 보낼 수 있다.

    ```html
     <ModalWhite :원룸들= "원룸들" :clickPrd="clickPrd" :openMd = "openMd"/>
    ```
2.  자식컴포넌트에서 받은 데이터를 props로 등록한다.(각 데이터의 자료형을 적어준다)

    ```javascript
    name : "ModalWhite",
    props :{
        원룸들 : Array,
        clickPrd : Number,
        openMd: Boolean,
    }
    }
    ```

