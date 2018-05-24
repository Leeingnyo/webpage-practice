# comment form answer

[문제로](README.md)

## 1. 작성 버튼

### 1) button type 바꾸기

```html
<form>
  <textarea></textarea>
  <button type="button">작성</button>
</form>
```

이러면 submit이 안 일어난다.
그러니 그냥 button에 click 이벤트를 걸어서 쓰면 된다.

하지만 이 방법은 모바일 키패드 등 submit 버튼으로 활성화가 되지 않기 때문에 추천하지 않는다.

### 2-1) submit 이벤트 사용하기

`Event.preventDefault` 함수를 쓰면 된다.

```js
document.querySelector('form').onsubmit = function (event) {
  event.preventDefault();
};
```

### 2-2) submit 이벤트 사용하기

`false` 를 return 하면 위와 같다고 한다. jQuery handler와는 다르니 주의. 이 [스택오버플로우 답변](https://stackoverflow.com/questions/1357118/event-preventdefault-vs-return-false) 참고.

```html
<form>
  <textarea></textarea>
  <button>작성</button>
</form>
<script>
document.querySelector('form').onsubmit = function () {
  return false;
};
</script>
```

### 3) onclick 이벤트에서 버블링 막기

type이 submit인 button 에서 `click` 이 일어났기에 여기서 onsubmit 으로 버블 업 할 것이다 (아마ㅠ). 그러니 onclick callback 에서 preventDefault 나 return false; 를 해줘도 된다.

```js
document.querySelector('button').onclick = function (event) {
  event.preventDefault();
  // return false;
};
```

## 2. 버튼을 오른쪽으로

```css
button {
  width: 80px;
  height: 30px;
  box-sizing: border-box;
  border: none;
}
```

를 기본 css 라고 생각하고 밑에 답을 쓰겠습니다.

### 1) position: absolute;

```css
.button-wrapper {
  position: relative;
  padding-bottom: 30px;
}
button {
  position: absolute;
  right: 0;
}
```

### 2) position: relative;

```css
.button-wrapper {
  position: relative;
}
button {
  position: relative;
  left: calc(100% - 80px);
}
```

`left: 420px;` 로 하시는 분들도 있는데, 가로폭이 줄어들거나 버튼 크기가 바뀌는 요구조건이 생길지도 모르니 calc() 를 써서 계산해줍시다.

### 3) margin: 0 0 0 auto;

```css
button {
  display: block;
  /* margin: 0 0 0 auto; */
  margin-left: auto;
}
```

### 4) float: rigiht;

```css
.button-wrapper {
  overflow: auto;
}
button {
  float: right;
}
```

### 5) text-align: right;

```css
.button-wrapper {
  text-align: right;
}
```

2개는 생략.

위 5개는 때에 따라 답이 다르겠지만, 미래에 작성버튼 옆에 다른 버튼들이 생긴다거나 크기가 바뀐다든가, 새로 생긴 다른 버튼 중 몇개는 왼쪽 정렬, 몇개는 오른쪽 정렬이고 이렇다고 가정하면...

flex가 제일 좋겠네요ㅎㅎ

## 3. 댓글 넣기

```html
<textarea class="form"></textarea>
<ul class="comment-list">
</ul>
```

로 있으면

### 1) jQuery 사용

```js
var content = $('.form').val();
$('.comment-list').append('<li>'+content+'</li>');
```

### 2) Vanilla JS 사용

```js
var content = document.querySelector('.form').value;
document.querySelector('.comment-list').ineerHTML += '<li>'+content+'</li>';
```

!주의! 입력에서 html escape 도 해줘야 합니다.
전 귀찮아서 안 함.
