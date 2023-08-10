---
description: vue에서의 조건문
---

# 🤔 v-if 와 모달창 만들기



### 🙂 Vue로 동적인 UI 만드는 Step

1. 현재 HTML UI의 상태를 데이터로 저장한다. (현재 보이는지 안보이는지 등)
2. 그 상태에 따라 HTML UI를 보여줄지 말지를 Vue 문법으로 작성한다.

즉, 현재 상태를 먼저 만들어두고 문법으로 제어한다는 말인거 같다.





#### ✍️ HTML 작성

```markup
<div class="black-bg">
  <div class="white-bg">
    <h4>상세페이지</h4>
    <p>상세페이지내용임</p>
  </div>
</div>
```



#### ✍️ CSS 작성

```css
body {
  margin : 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height:100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
} 
```





### 1. 모달창 현재상태 data에 저장

```javascript
data(){
  return {
    openMd : false,
  }
}
```

기본 상태에서는 false 로 두어 false 상태에서는 숨기고 true일때는 나타나도록 기능 개발을한다.





### 2.  v-if 기능

기본 상태에서는 숨기고 상품제목을 눌렀을때만 모달창이 열리도록  하기 위해서

HTML 태그 안에 <mark style="background-color:red;">**v-if="조건식"**</mark>을 사용하여 조건식이 참일 때만 모달창이 열리게 코드를 작성한다.

```html
<div class="black-bg" v-if="openMd == true" >
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
    </div>
  </div>
  

<div>
  <img src="./assets/room0.jpg" class="room-img">
  <h4 @click="openMd = true"> {{products[0]}} </h4>
  <p> 50 만원</p>
  <button @click="신고수[0]++">허위매물신고</button> <span>신고수 : {{신고수[0]}} </span>
</div>
```





숙\[제]]
