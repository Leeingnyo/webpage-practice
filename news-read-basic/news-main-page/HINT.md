# news main page hint

[문제로](README.md)

## 1. 최소 조건 만족하기

HTML5에 와서 많은 태그들이 추가됐다.
그 중 semantic element 라는 걸 알아봤으면 좋겠다.

태그 자체에 의미가 들어가게 됐단 건데

```html
<div class="figure">
  <img alt="이미지">
  <p class="caption">캡션</p>
</div>
```

가

```html
<figure>
  <img alt="이미지">
  <figcaption>캡션</figcaption>
</figure>
```

로 바뀐 거라고 보면 된다. 태그만 보고 안에 있을 내용을 유추해낼 수 있는 것이다.
아니라면 id나 class를 보고 읽어야 하는데 여기는 단순 CSS 만을 위해 들어있을 수도 있어서 분석이 어렵다.
이를 잘 지키면 보조 도구(웹 페이지 읽어주기 등)나 검색엔진, 페이지 요약 등에 유리할 거다.

자세한 건 [여기](https://www.w3schools.com/html/html5_semantic_elements.asp)를 참고.

div, span은 최대한 안 써본다고 생각하고 구성해보자.
