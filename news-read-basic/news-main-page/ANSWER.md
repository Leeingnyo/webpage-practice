# news main page answer

[문제로](README.md)

## 1. 최소 조건 만족하기

다시 말하지만 정답이 없다는 점을 잘 알아두자.

이 문제에서 쓰일만한 semantic element 들은

* article
* main
* header

이 정도로 볼 수 있을 것 같다.

그리고 뉴스 목록을 나타내야 하니까 list 관련 태그인 순서없는 리스트 ul 태그, 그리고 list item 인 li 태그를 쓰면 될 것 같다.

뉴스는 제목과 본문으로 이루어져 있으니 heading tag와 paragraph tag를 사용하면 될 것이다. 기사 하나 내부에서 제일 큰 기사의 제목이므로 h1을 쓰고 첫 단락에는 p를 쓸 것 같다.

'~ 것 같다.'라고 표현하는 이유는 정답은 존재하지 않기 때문이다.
여기다가는 내가 생각하기에 옳다고 생각하는 걸 근거와 함께 얘기하고 있는 중이니 여러분들 자신만의 생각을 갖고 작성해도 좋다. 
나는 기본 CSS 만으로도 예쁘게 보였으면 좋겠다는 생각을 하고 있어서 태그 의미를 살리며 작성하는게 좋다.

```html
<header>
  <h1>ㅇㅇ 뉴스</h1>
  <!-- 페이지의 첫 부분이다. -->
</header>
<main>
  <!-- 페이지의 주 내용에 해당한다. -->
  <h2>뉴스 목록</h2>
  <ul>
    <!-- 목록인데 순서가 중요하지 않으니 unordered list, ul 를 썼다. -->
    <li>
      <!-- list item, li 를 썼다. -->
      <article>
        <!-- 기사 하나는 article tag로 감쌌다. 각 태그 설명을 한 번 읽어보자. -->
        <h1>나노스, 美 솔크 연구소에 투자...바이오 사업 기반 확보</h1>
        <p>나노스는 미국 샌디에이고에 위치한 `솔크연구소(Salk Institute)`에 기부형식으로 150만달러를 투자했다고 23일 밝혔다. 나노스는 이를 통해 바이오 사업 진출을 위한 기반을 확보할 계획이다.</p>
      </article>
    </li>
    <li>
      <article>
        <h1>"일찍 온 여름… 식중독 주의하세요" 식약처 주의당부</h1>
        <p>식품의약품안전처는 일찍 찾아온 더위로 병원성대장균 식중독 발생위험이 높아짐에 따라 음식물의 조리·보관·섭취에 각별히 주의할 것을 당부했다.</p>
      </article>
    </li>
    <li>
      <article>
        <h1>죽상동맥경화증, '치료제 개발 가능성' 찾아</h1>
        <p>국내 연구진이 최근 연구를 통해 혈관내 콜레스테롤 제거에 관여하는 유전자를 최초로 발견해 주목된다.</p>
      </article>
    </li>
  </ul>
</main>
```

article 태그 안에도 h1 을 header로 감싸도 좋고, p 부분을 main으로 감싸도 좋다. 각각 의미를 잘 살리고 있기 때문에 상관없다.
근데 너무 장황한 것 같아서 뺐고, 만약 다른 요소들이 추가된다면 (부제목, 기자, 기사 작성 시간 등) article 내부도 header, main, aside 로 나누고 time 등을 활용할 것 같다.
하여간 정답은 없다!
div와 span을 줄인다는 방향으로 생각해보자.

## 2.  최신 뉴스 부분과 조회수 부분 나누기

구획을 구분하는 section 태그를 활용해서 부분을 나눌 것이다.

```html
<header>
  <h1>ㅇㅇ 뉴스</h1>
</header>
<main>
  <section id="recent-news">
    <h2>최신 뉴스</h2>
    <h3>뉴스 목록</h3>
    <ul>
      <li>
        <article>
          <h1>나노스, 美 솔크 연구소에 투자...바이오 사업 기반 확보</h1>
          <p>나노스는 미국 샌디에이고에 위치한 `솔크연구소(Salk Institute)`에 기부형식으로 150만달러를 투자했다고 23일 밝혔다. 나노스는 이를 통해 바이오 사업 진출을 위한 기반을 확보할 계획이다.</p>
        </article>
      </li>
      <li>
        <article>
          <h1>"일찍 온 여름… 식중독 주의하세요" 식약처 주의당부</h1>
          <p>식품의약품안전처는 일찍 찾아온 더위로 병원성대장균 식중독 발생위험이 높아짐에 따라 음식물의 조리·보관·섭취에 각별히 주의할 것을 당부했다.</p>
        </article>
      </li>
    </ul>
  </section>
  <section id="popular-news">
    <h2>조회수가 높은 뉴스</h2>
    <h3>뉴스 목록</h3>
    <ul>
      <li>
        <article>
          <h1>죽상동맥경화증, '치료제 개발 가능성' 찾아</h1>
          <p>국내 연구진이 최근 연구를 통해 혈관내 콜레스테롤 제거에 관여하는 유전자를 최초로 발견해 주목된다.</p>
        </article>
      </li>
      <li>
        <article>
          <h1>"일찍 온 여름… 식중독 주의하세요" 식약처 주의당부</h1>
          <p>식품의약품안전처는 일찍 찾아온 더위로 병원성대장균 식중독 발생위험이 높아짐에 따라 음식물의 조리·보관·섭취에 각별히 주의할 것을 당부했다.</p>
        </article>
      </li>
      <li>
        <article>
          <h1>나노스, 美 솔크 연구소에 투자...바이오 사업 기반 확보</h1>
          <p>나노스는 미국 샌디에이고에 위치한 `솔크연구소(Salk Institute)`에 기부형식으로 150만달러를 투자했다고 23일 밝혔다. 나노스는 이를 통해 바이오 사업 진출을 위한 기반을 확보할 계획이다.</p>
        </article>
      </li>
    </ul>
  </section>
</main>
```

id로 정확한 이름도 지어줬다.

구조와 관련 해서는 [여기](https://developer.mozilla.org/ko/docs/Web/HTML/HTML5_%EB%AC%B8%EC%84%9C%EC%9D%98_%EC%84%B9%EC%85%98%EA%B3%BC_%EC%9C%A4%EA%B3%BD)를 참고하면 좋을 것 같다.
