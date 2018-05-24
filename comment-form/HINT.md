# comment form hint

[문제로](README.md)

## 1. 작성 버튼 눌렀을 때 작성되게 하기

이 문제는 `<form>` 안의 `<button>` 는 `type=submit`이 default 라는 것을 알고, 그것을 막는 것을 알아보는 문제이다.
아마 그냥 `<form>` 안에 `<button>`을 넣고 버튼을 누르면 새로고침이 일어나게 될 것이다
(`<form>`의 `method` 는 GET, `action` 은 현재 페이지로 이동할 것이기 때문).
이를 막기 위한 방법은 3가지가 있으니 찾아서 해결해보도록 하자.

### 찾아보면 좋은 키워드

* button tag attribute type
* onsubmit event
* event prevent

## 2. 버튼을 오른쪽으로

위치 옮기는 건 유서깊은 문제. 저렇게 보이게 끔 하는 해결 방법은 6가지 쯤 된다.

### 찾아보면 좋은 키워드

* position absolute
* position relative
  * calc()
* margin
  * auto
* float
  * overflow
* text-align
* flex
* grid

## 3. 화면에 그리기

DOM을 만들고 넣는 법을 알아야 한다.
jQuery 쓰면 편한데 Vanilla 로도 할 순 있다.

### 찾아보면 좋은 키워드

* jQuery append
* innerHTML
* createElement
* Element.appendChild
