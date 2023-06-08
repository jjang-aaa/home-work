# Position 과제
- 완성본 이미지

<img width="473" alt="home-work-screenshot" src="https://github.com/jjang-aaa/home-work/assets/131199065/2dc288a5-5924-472e-875f-3758f7fb2270">

- 주어진 과제
    - 마크업 순서는 1. 로그인(제목), 2. 아이디 레이블과 입력서식, 3. 비밀번호 레이블과 입력서식, 4. 로그인 버튼, 5. 회원가입 및 아이디/비밀번호 찾기 링크 순으로 구현한다.
    - 이미지 assets 없이 모든 디자인을 CSS로 구현한다.
    - 일부 요소의 배치를 position 속성을 활용하여 구현한다.
-----
## HTML 코드 설명
- HTML 코드 전체를 설명을 위해 간략하게 나타냈습니다.

```html
<div class="login-box">
  <h1>로그인</h1>
  
  <div class="login-group">
    <form>
        <fieldset>
          <legend>로그인</legend>
          <label>아이디</label>
          <input type="email"/><br/>
          
          <label>비밀번호</label>
          <input type="password"/>
        </fieldset>
    </form>
    
    <button>로그인</button>
    
    <div class="login-help">
      <img/>
      <a>회원가입</a>
      <img/>
      <a>아이디 비밀번호 찾기</a>
    </div>
    
  </div>
  
</div>
```

#### login-box div
- 전체 주황색 박스를 만들기 위해 생성했습니다.
- 내부에 `h1` 태그, `login-group div`를 가지고 있습니다.

#### login-group div
- 흰 박스를 만들기 위해 생성했습니다.
- 내부에 `form`, `button`, `login-help div`를 가지고 있습니다.

#### form
- 로그인 폼을 생성했습니다.
- 로그인 폼 안에 아이디 `label`과 `email input`, 비밀번호 `label`과 `password input`을 가지고 있습니다.
- 아이디는 이메일 작성을 쉽게 하기 위해 `email type`을 사용했고, 비밀번호는 보안을 위해 `password type` 을 사용했습니다.

#### button
- 로그인 버튼으로 사용했습니다.

#### login-help div
- 아이콘이미지, 회원가입, 아이디 비밀번호 찾기 링크를 가지고있습니다.
- 주어진 것은 아이콘 폰트 사용이었고, 추가하지 않아도 된다고 했지만 너무 허전해서 이미지 삽입으로 대체하여 마무리하였습니다.
-----
## CSS 코드 설명

#### .login-box
```css
    margin-top: 50px;
    margin-left: 50px;
```
- 웹 페이지에서 편하게 보기위해 추가했습니다.

#### legend와 fieldset

```css
legend {
  position: absolute;
  top: 0;
  left: 0;
  width: 0;
  height:0;
  overflow:hidden;
  display: none;
  font-size: 0;
  line-height: 0;
}

fieldset {
  border: 0;
  padding: 0;
  padding-bottom: 5px;
  margin-right: 10px;
  border-bottom: 1px solid rgba(204, 204, 204, 1);
}
```
- `legend`와 `fieldset`이 폼 영역을 감싸는 부분을 없애기위해 사용한 코드이고 로그인 칸 안의 회색 라인을 `fieldset` 아래에 적용해서 만들었습니다.

#### position
- `h1`, `.login-group`, `.login-from` 을 포지션 `relative`를 통해 위치를 지정했습니다.
- `button`은 `absolute`를 통해 `login-group div`를 기준으로 위치를 지정했습니다.

#### float
- 이미지와 회원가입, 아이디 비밀번호 찾기(`.sign-up`, `.find-id-password`, `.sing-up-icon`, `.find-icon`)를 `float`을 통해 정렬했습니다.

-----
## 문제점

- 처음에 구상을 머릿속으로 대충하고 만들면서 수정해야지 하는 생각으로 시작했다가 배치를 적용하는 부분에서 내가 어떤 부분을 왜 움직이고 있는지 헷갈려서 배치하기가 힘들었습니다.
- 배치할 때 사용하는 포지션의 `relative`와 `absolute` 의 작동원리를 이해하지 못해서 사용하기 어려웠습니다.
-----
## 해결방안
- 만들려고한 구조를 그림으로 그려보았습니다.
- 어느 위치의 무엇을 적용하고 있는지 html 코드와 구조를 그린 그림을 함께 계속 확인하며 css 코드를 작성했습니다.
- 포지션의 `relative`와 `absolute` 의 작동원리에 대해 이듬강의 시청과 검색을 통해 작동하는 형태를 이해하려 했습니다.
##### relative
- `relative`를 적용하는 요소만 그 위치에 나와서 위치를 움직일 수 있습니다. 내가 나온 위치에서 상대적으로 움직입니다.
##### absolute
- `absolute`를 적용한 요소의 본래 위치는 제거되고 이 요소가 있는 곳에서 가장 가까운 부모를 기준으로 위치가 지정되어 움직일 수 있습니다.
-----
## 느낀 점
- 코드를 작성하기 전 구조를 그려서 시각적으로 이해하는 것이 중요하고, 코드를 작성하면서 이 코드의 의미를 지속적으로 되짚어보는 것이 중요하다고 생각했습니다. 그래야 이 코드가 어디에 어떻게 사용되는지 스스로 이해가 가능하고 내가 어디를 작성하고 있는지 파악할 수 있습니다.
- 태그나 속성 등을 사용할 때 어떤 원리인지 어떻게 작동하는지를 파악하고 사용해야한다는 것을 다시한번 깨달았습니다.
- 코드를 작성할 때 최대한 내가 쓴 이유를 설명할 수 있도록 하자 라고 생각하며 작성했지만 아직 논리적으로 설명하기에 부족하다고 느꼈습니다.
- 내가 내 코드를 이해하며 읽을 수 있는 것이 중요하다고 생각합니다.
