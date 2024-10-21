# ➕ 문자열 덧셈 계산기

> **구분자**와 **양수**로 이루어진 문자열에서 숫자를 추출하여 더하는 계산기를 구현한다.

### 구분자

- 구분자는 한 글자로 제한한다.
- 기본 구분자는 `,`, `:` 이다.
- 커스텀 구분자를 사용할 수 있다.
    - 커스텀 구분자를 사용할 때, 기본 구분자는 사용할 수 있다.
    - 커스텀 구분자는 최대 1개까지 등록할 수 있다.
    - 추가할 커스텀 구분자는 문자열 앞부분의 `//`와 `\n` 사이에 위치한다.
        - 예) `//;\n1,2:3;4.5!6` ->  기본 구분자(`,`, `:`) + 커스텀 구분자(`;`) 사용 가능
    - **단, 커스텀 구분자에 `\ `, `숫자`, `이모지`는 사용할 수 없다.**
        - 예) `//\\n~`, `//7\n~`, `//🤫\n~` -> `IllegalArgumentException` 발생

### 숫자

- 숫자는 양수로만 이루어져 있다.
- 계산 결과는 `0 ~ 2,147,483,647`이다.
    - 숫자가 아니거나 계산 결과가 `2,147,483,647`을 초과하는 경우 -> `IllegalArgumentException`을 발생

### 계산식

- 기본 구분자
    - 입력된 문자열 = 계산식
- 커스텀 구분자
    - 입력된 문자열 = (`//[커스텀 구분자]\n`) + 계산식

### 실행 결과 예시

```text
덧셈할 문자열을 입력해 주세요.
1,2:3
결과 : 6
```

---

## ⚙️ 기능 목록

- [x] 입력한 문자열에서 숫자를 추출하여 더하는 계산기
    - [x] 기본 구분자( `,`, `:` )를 가지는 문자열을 전달하는 경우
    - [x] 커스텀 구분자를 가지는 문자열을 전달하는 경우
- [ ] 예외 상황 (`IllegalArgumentException`) 처리
    - [ ] **잘못된 계산식 패턴**
        - [ ] 올바른 구분자가 아닌 경우
        - [ ] 구분자가 연속으로 나오는 경우
        - [ ] 계산식 양 끝이 숫자가 아닌 경우
    - [x] **사용자 입력이 잘못된 경우**
        - [x] 숫자가 음수인 경우
        - [x] 숫자가 아닌 경우
    - [ ] **커스텀 구분자**
        - [ ] 구분자 입력 패턴이 잘못된 경우 (`^//[커스텀 구분자]\n`)
        - [ ] 구분자가 입력되지 않은 경우
        - [ ] 구분자가 2개 이상인 경우
        - [ ] 불가능한 구분자가 입력된 경우
            - [ ] 구분자가 숫자인 경우
            - [ ] 구분자가 이모지인 경우
            - [ ] 구분자가 `\ `인 경우

---

## 📚 참고 문서

- [WikiPedia: 구분 문자](https://w.wiki/Bc3r)