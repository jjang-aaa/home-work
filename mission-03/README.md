# Transition 과제
- 완성본 gif

![trasition-home-work](https://github.com/jjang-aaa/home-work/assets/131199065/7275ee61-5b60-4935-9bfa-38f6f19d9e8a)

- 주어진 과제
    - 관련 사이트는 제목으로 각각 항목은 링크로 구현한다.
    - 링크 목록은 5개이며 CSS를 사용하여 화면에 1개의 목록만 보이도록 구현한다.
    - 목록에 마우스를 올리면 5개의 목록이 펼쳐지도록 구현한다.
    - transition 속성을 활용하여 애니메이션 효과를 적용한다.
-----
## HTML 코드 설명


```html
<body>
 <div class="site-box">
  <h1>관련 <span>사이트</span></h1>
  
  <div class="site-list-box">

    <ul class="site-list">
      <li><a href="/">제로베이스</a></li>
      <li><a href="/">MDN</a></li>
      <li><a href="/">웹 접근성 연구소</a></li>
      <li><a href="/">Web Standards</a></li>
      <li><a href="/">W3C</a></li>
    </ul>
    
  </div>
  
</div>
</body>
```
### 구조
- `site-box <div>` 안에 `<h1>` 제목태그와 `site-list-box <div>`가 있습니다.
- `site-list-box <div>` 안에 `<ul>` 태그로 목록을 정렬합니다.
- 목록은 `<a>` 태그를 적용했습니다.
- `<h1>`에 `<span>`을 넣어 색을 적용했습니다.
-----
## CSS 코드 설명

### site-box 와 site-list-box 코드 일부분
```css
.site-box {
    margin: 50px 0 0 50px; /* 화면에 보기 편하게 하기 위해 작성 */
    padding: 0;
    transition: padding 400ms linear;
}

.site-box:hover {
    padding-bottom: 120px;
    transition: padding 400ms linear;
}

.site-list-box {
  overflow: hidden;
  padding: 0;
  transition: padding 400ms linear;
}

.site-list-box:hover {
  padding-bottom: 120px;
  transition: padding 400ms linear;
}
```
- 박스들은 마우스를 올리면 패딩을 통해 펼쳐져보이게 구현했습니다.
- linear 값을 주어 직선형태로 내려오게 했습니다.
- 목록을 하나로 보이게 하기위해 `overflow: hidden;`을 사용했습니다.

### site-list

```css
.site-list {
  list-style: none;
  margin: 5px 0 0 25px;
  padding: 0;
  transition: padding-top 400ms 450ms ease-out;
}

.site-list:hover {
  padding-top: 15px;
  transition: padding-top 400ms 450ms ease-out;
}
```
- `list-style`을 없애고 남은 공간을 마진과 패딩으로 위치를 조정했습니다.
- `padding-top`에 공간을 주고 `delay`시간을 조금주어서 목록들이 더 늦게 내려오고 올라가도록 만들었습니다.
- `ease-out`을 사용해 끝에서 조금 느려지는 애니메이션을 구현했습니다.
-----
## 해결되지 않은 점
- 목록에 마우스를 올리면 목록 리스트, 흰 박스와 회색 박스 모두 펼쳐지는데 회색 박스에 마우스를 올리면 회색 박스만 펼쳐지게 됩니다.
- 세 부분이 한번에 펼쳐지도록 구현하고 싶었으나 구조적인 문제인지 방법을 찾지 못해서 해결하지 못한 부분이 있습니다.
-----
## 느낀 점
- 구조를 설계하면서 어떤 태그를 쓰면 좋을지 아직 바로 떠올리지 못하는 점이 아쉬웠습니다.
- 이번 과제는 깔끔하게 어디에 무엇을 적용하는지 이해하고 작성해서 뿌듯했습니다.
