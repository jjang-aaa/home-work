# Sprite 과제
#### 완성본 이미지

<img width="330" alt="sprite-home-work" src="https://github.com/jjang-aaa/home-work/assets/131199065/97663afb-b7a5-49e1-905f-ccb6e4858431">

#### 주어진 과제

- 더보기 링크 앞에 플러스 기호는 생략해도 무방하다.
- rank.png(webcafe-RWD/assets 폴더에 있음) 이미지를 활용하여 스프라이트 기법으로 스타일링 한다.
- 각 인기 사이트의 순위를 나타내는 영역은 기존 `<ol>` 요소에서 제공하는 기본 숫자를 보이지 않도록 한 후 CSS로 구현한다.

-----
## HTML 코드 설명
```html
<body>
  <div class="popularSite__container">
    <h2 class="popularSite">인기 
    <span class="orangePoint">사이트</span></h2>

    <ol class="popularSite__list">
      <li class="popularSite__item w3c">
      <a href="/">W3C</a></li>

      <li class="popularSite__item webStandard">
      <a href="/">Web Standard</a></li>

      <li class="popularSite__item cssZenGarden">
      <a href="/">CSS ZenGarden</a></li>

      <li class="popularSite__item mdn">
      <a href="/">MDN</a></li>
    </ol>

    <a href="/" class="popularSite__more" 
    title="인기 사이트 더보기">더보기</a>
  </div>
</body>
```

### 구조
- 인기사이트의 `<div>`로 컨테이너를 만들고 그 안에 제목, 인기사이트 리스트, 더보기 순으로 작성했습니다.
- 제목`<h2>`의 '사이트' 색을 위해 `<span>`을 사용했습니다.
- 인기사이트 리스트는 `<ol>`태그로 마크업했습니다.
- `<li>`에는 링크와 사이트명을 적고 나열했습니다.
- 더보기도 인기사이트의 더보기로 가는 `<link>`태그로 마크업하고 `title`속성으로 인기사이트 더보기임을 표시했습니다.

-----
## CSS 코드 설명

```css
/* 인기 사이트 */
.popularSite__item {
  font-size: 11px;
  margin-bottom: 8px;
  counter-increment: number;
  position: relative;
}

/* 인기 사이트 순번 */
.popularSite__item::before {
  content: counter(number);
  color: white;
  background-color: rgba(163, 163, 163, 1);
  display: inline-block;
  text-align: center;
  padding-top: 2px;
  width: 16px;
  height: 14px;
  border-radius: 5px;
  margin-right: 4px;
}

/* 인기 사이트 랭크 */
.popularSite__item::after {
  content: "";
  position: absolute;
  right: 0;
  background: url(./image/rank.png) no-repeat;
  width: 12px;
  height: 17px;
}

.w3c::after {
  background-position: 0 3px;
}

.webStandard::after {
  background-position: 0 -42px;
}

.cssZenGarden::after {
  background-position: 0 -19px;
}

.mdn::after {
  background-position: 0 3px;
}
```
#### CSS만으로 순번모양 구현
- 인기사이트 앞의 순번 모양을 만들기 위해 `::before`을 사용하였습니다.
- 인기사이트 아이템에 `counter-increment: number;`를 지정하여 순서를 1씩 증가시켰습니다. 숫사를 생략하면 기본값은 1이며,`list-item <ol>`요소를 사용했기때문에`counter-reset`을 할 필요없이 생성된 순서대로 순번이 지정되었습니다.
- 크기지정을 위해 `.popularSite__item::before `에 `display: inline-block;`으로 지정했고 `content: counter(number);`를 통해 값을 표시하도록 했습니다.
#### rank부분 image sprite 사용
- 인기사이트 랭크부분을 `position: absolute;`로 위치설정을 하기위해 인기사이트 아이템을 `position: relative;`지정했습니다.
- 인기사이트 아이템에 `image sprite`를 사용하기 위해 `::after`을 만들고 background에 이미지를 지정했습니다.
- 그리고 `position: absolute;`을 지정해 `background-position`로 위치를 설정했습니다.

```css
/* 인기 사이트 컨테이너 */
.popularSite__container {
 width: 190px;
 height: 147px;
 background: linear-gradient(to bottom, rgba(204, 204, 204, 1),
 rgba(238, 238, 238, 1));
 border: 1px solid rgba(163, 163, 163, 1);
 border-radius: 5px;
 position: relative;
}

/* 인기 사이트 더보기 */
.popularSite__more {
  font-size: 14px;
  position: absolute;
  top: 0;
  right: 0;
  margin: 12px;
}
```
#### 더보기 구현
- 더보기를 `position: absolute;`로 위치설정을 위해 컨테이너에 `position: relative;`를 지정하였습니다.

-----
## 느낀 점

- *image sprite*를 사용해보는게 재미있었습니다. *background*로 설정하니깐 왠지 깔끔해보이는 느낌이 들었습니다.
- 이번 과제에 *position*을 잘 사용한 것 같아 뿌듯했습니다.
- 가상요소인 *::before*와 *::after* 사용에 대해 더 이해할 수 있게 되었습니다.
- 텍스트나 이미지 같은 요소들이 박스 안에 있으면 한번에 중앙 정렬이 가능한 속성만 찾아서 써야할 것 같아서 마진, 패딩으로 구현하는게 맞을까...? 하는 의문이 들었습니다.
