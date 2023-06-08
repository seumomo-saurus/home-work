# 멋쟁이 사자처럼 프론트엔드 스쿨 6기 2번째 과제

## 로그인 박스 만들기

![목표 사진](./completed.png)

### 조건

- 마크업 순서
  1. 로그인(제목)
  2. 아이디, 비밀번호(레이블과 입력 서식)
  3. 로그인 버튼
  4. 회원가입 및 아이디 비밀번호 찾기(링크)
- 이미지 없이 모든 디자인을 CSS로 구현
- position 속성 활용
- 회원가입 및 아이디 비밀번호 찾기 영역은 float를 활용

<br>

## 코드 설명

### HTML

1. 큰 박스(loginBox) 설정
2. 대제목 설정
3. label과 input 요소를 그룹화(idBox, pwBox)
4. 아이디와 비밀번호 각 2개의 그룹을 그룹화(idPwBox)
5. idPwBox와 로그인 버튼을 form으로 그룹화
6. 2개의 link 요소(회원가입, 아이디 비밀번호 찾기)를 그룹화(subBox)

```
<div class="idBox">
  <label for="inputID" class="inputIdLabel">아이디</label>
  <input
    type="email"
    id="inputID"
    placeholder="euid@euid.dev"
    required
  />
</div>
```

- 아이디는 email 유형으로 받도록 type의 값을 email로 함
- placeholder에 값을 줘서 email의 예시를 보여줌
- required 속성으로 필수로 입력받을 수 있도록 함

<br>

```
<div class="pwBox">
  <label for="inputPW" class="inputPwLabel">비밀번호</label>
  <input
    type="password"
    id="inputPW"
    placeholder="8자리 이상"
    required
    minlength="8"
  />
</div>
```

- 최소 8자리 이상 입력하도록 minlength의 값을 8로 주었고, placeholder의 값으로 최소 입력 자릿수를 안내함

<br>

```
<label for="loginBtn" hidden>로그인</label>
<button type="submit" id="loginBtn">로그인</button>
```

로그인 버튼에 label을 삽입하였으나 hidden 속성으로 읽히고 보이지 않도록 함

<br>

### CSS

```
* {
  box-sizing: border-box;

  padding: 0;
  margin: 0;

  font-family: "Pretendard";
  font-style: normal;
}
```

모든 박스를 기본적으로 border-box로 설정하였고, padding, margin값을 0으로 초기화함

<br>

```
.loginForm {
  position: relative;

  padding-bottom: 8px;

  border-bottom: 1px solid gray;
}
```

자식 요소(로그인 버튼)의 position 값을 absolute로 주기 위해 position 값을 지정함

<br>

```
.inputIdLabel,
.inputPwLabel {
  position: relative;
  top: 4px;
}
```

각 레이블의 위치가 시안 대비 약간 높게 설정되어 있어 자신의 위치를 기준으로 살짝 내리기 위해 position 및 top 값 설정

<br>

```
#inputID {
  position: absolute;
  right: 0;
}

#inputPW {
  position: absolute;
  right: 0;
}

#loginBtn {
  position: absolute;
  top: 0;
  right: 0;

  width: 50px;
  height: 53px;

  border: 0;
  border-radius: 5px;

  background-color: #ed552f;

  color: white;
  font-size: 13px;
  font-weight: 400;
}
```

input 요소와 로그인 버튼의 position을 absolute로 하고 시안에 맞게 위치를 위치를 조정

<br>

```
.signUp {
  float: left;

  width: 62px;
  padding-top: 4px;

  text-align: right;
  font-size: 13px;
  line-height: 150%;
}

.searchIdPw {
  float: left;

  width: 125px;
  padding-top: 4px;
  margin-left: 17px;

  text-align: right;
  font-size: 13px;
  line-height: 150%;
}

```

회원가입과 아이디 비밀번호 찾기를 float를 활용하여 배치

<br>

```
.signUp::before {
  content: "▶";
  float: left;
  display: block;

  margin-right: 4px;
}

.searchIdPw::before {
  content: "▶";
  float: left;
  display: block;

  margin-right: 4px;
}
```

회원가입과 아이디 비밀번호 찾기 텍스트 앞에 가상 요소 선택자를 활용하여 특수문자를 삽입

<br>

## 결과물

![결과 사진](./mycompleted.png)

가장 큰 박스에 그라데이션이 들어간 듯한 색을 제외하고 완료하였다.

width와 height를 주지 않아도 될 요소와 줘야 할 요소가 구분이 어려웠고, 주석으로 지워도 결과물이 바뀌지 않는 값들은 삭제하였다.
