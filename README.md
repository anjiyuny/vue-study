---
description: HTML에 데이터 꽂아넣는 Vue 데이터바인딩 문법
---

# 👩💻 데이터 바인딩

쇼핑몰 사이트를 만든다고 가정해보자.

먼저 `template` 안에 레이아웃 부터 작성해본다.

```html
<template>
  <div>
    <h4>XX 원룸</h4>
    <p>XX 만원</p>
  </div>
  <div>
    <h4>XX 원룸</h4>
    <p>XX 만원</p>
  </div>
</template>

```





### 🙂Vue 의 데이터 바인딩 문법

1. **데이터를 어딘가에 보관하고**
2. **\{{ 데이터 \}} 문법으로  HTML중간에 넣으면 완성!**



```javascript
export default {
  name : 'App',
  data(){
    return {
      price1 : 60
    }
  }
}
```

script 태그 안에 <mark style="background-color:yellow;">**data( ){ return { } }**</mark> 작성한 후에

데이터를 object 형식으로 저장하면 된다.

이게 <mark style="color:red;">vue의 data 보관함, 변수 보관함이라고 생각하면 된다고 한다.</mark>

```markup
<p>{{price1}} 만원</p>
<!-- 60 만원 이라고 출력됨 -->
```





### 🙂데이터바인딩을 사용하는 이유

1. 가격이 매일 변동하는 쇼핑몰이라고 가정하면 수정이 편리 해 진다.
2. data가 변경되면 data와 관련된 HTML에 실시간으로 반영되는 실시간 렌더링기능을 쓸 수 있다.





### 🙂html속성도 데이터바인딩이 가능하다



color 같은속성도 data에 저장해두고 **콜론을 찍고** 불러오면 된다.

&#x20; <mark style="background-color:red;">**:style = "데이터이름"**</mark>  &#x20;

```markup
<template>
  <div>
    <h4 :style="스타일">XX 원룸</h4>
    <p>XX 만원</p>
  </div>
  <div>
    <h4>XX 원룸</h4>
    <p>XX 만원</p>
  </div>
</template>

<script>
export default {
  name : 'App',
  data(){
    return {
      price1 : 60,
      스타일 : 'color:red'
    }
  }
}

</script>
```
