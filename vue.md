---
description: click 이벤트를 알아보자
---

# 😇 Vue 이벤트 핸들러

아래와 같은 버튼을 만들어 클릭할때마다 신고수가 올라가는 기능을 구현해보자.

```markup
<div>
  <h4>{{products[0]}}</h4>
  <p>50만원</p>
  <button>허위매물신고</button>
  <span>신고수 : 0</span>
</div>
```





### 🙂vue : click 이벤트핸들러



자바스크립트에서는 onClick="" 이 있었지만

**vue에서는 **<mark style="background-color:orange;">**@click =""**</mark>** 이라고 사용한다.**

```markup
<div>
  <h4>{{products[0]}}</h4>
  <p>50만원</p>
  <button @click="신고수++">허위매물신고</button>
  <!-- 클릭할때마다 1씩-더해-신고수 카운트해주기 -->
  <span>신고수 : {신고수}</span>
</div>
```

물론 @click 뿐 아니라 mouseover등 다양한 이벤트 핸들러가 존재한다.





### 🙂코드가 길경우 함수로 만들어 쓴다

@click = "" 안에 들어갈 함수가 너무 길다면 함수를 만들어서 축약한다.



```javascript
data(){
  return {
    신고수 : 0,
  },
}

methods : { 
  increase(){ 
    this.신고수 += 1 
  } 
}
```

이렇게 method : {} 를 만들고 increase(){} 안에 원하는 함수를 만들어 넣으면 되는데

<mark style="background-color:orange;">**this.데이터이름**</mark>  이라고 사용하지않으면 오류가 나니까 조심해야한다.



위와 같이 함수로 만들어 축약했다면 html로 돌아가 아래와 같이 수정한다.

```markup
<div>
  <h4>{{products[0]}}</h4>
  <p>50만원</p>
  <button @click="increase()">허위매물신고</button>
  <span>신고수 : {신고수}</span>
</div>
```





### ☝️ 숙제&#x20;

* 세개의 버튼을 만들어 각 카운트 되는 기능 구현하기



```markup
<div>
  <h4> {{products[0]}} </h4>
  <p> 50 만원</p>
  <button @click="신고수[0]++">허위매물신고</button> <span>신고수 : {{신고수[0]}} </span>
</div>

<div>
  <h4> {{products[1]}} </h4>
  <p>60 만원</p>
  <button @click="신고수[1]++">허위매물신고</button> <span>신고수 : {{신고수[1]}} </span>
</div>

<div>
  <h4> {{products[2]}} </h4>
  <p>70 만원</p>
  <button @click="신고수[2]++">허위매물신고</button> <span>신고수 : {{신고수[2]}} </span>
</div>
```

```javascript
data(){
  return{
    신고수 : [0,0,0],
    메뉴들 : ['Home', 'Shop', 'About'],
    products : ['역삼동원룸', '천호동원룸', '마포구원룸']
  }
}
```



data에 신고수를 배열형태로 버튼의 갯수 만큼 만들어 각각의 버튼에 이벤트 핸들러를 걸어 제어 해 주었다.

<figure><img src=".gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>
