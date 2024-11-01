# MemberController

`MemberController`는 사용자 인증 및 회원 관리를 위한 API 엔드포인트를 제공합니다. 이 컨트롤러는 회원 로그인, 로그아웃, 회원가입, 아이디 및 비밀번호 찾기 등의 기능을 포함하고 있습니다.

## 주요 기능

### 1. 로그인 `login`

@@@1

  사용자 로그인 요청을 처리. 성공 시 세션에 사용자 정보를 저장, 쿠키로 아이디 저장
  -  입력: 아이디, 비밀번호, `rememberId`(아이디 저장)
  -  결과: 로그인 성공 시 홈으로 리다이렉트, 실패 시 에러 메시지와 함께 로그인 페이지로 이동

### 2. 로그아웃 `logout`

@@@2

-  사용자가 로그인된 세션을 무효화하여 로그아웃 처리하고, 홈 페이지로 리다이렉트.

### 3. 회원가입 `join`

@@@3
 
  -  새로운 사용자를 등록.
  - 입력: 사용자 정보 (이름, 아이디, 비밀번호, 이메일, 역할) -> 역할 수정 예정

### 4. 아이디 중복 확인 `/member/{memberId}` > 소연언니 이거 삭제할까말까 결과를 보여줄 수 없엉 ㅇㅇ !

### 5. 내 정보 조회 `myinfo`

@@@4
 
 - 로그인한 사용자의 정보를 조회, `myInfo` 페이지에 표시.
 - 로그인되지 않은 경우 로그인 페이지로 리다이렉트.

### 6. 비밀번호 확인 `check-password`

@@@5
 
  현재 비밀번호가 올바른지 확인.
  - 입력: 비밀번호
  - 결과: `valid`(유효), `invalid`(유효하지 않음) 문자열로 결과 반환

### 7. 회원 탈퇴 `delete`

@@@6

  로그인된 사용자의 회원 탈퇴를 처리하고, 세션을 종료.

### 8. 회원 정보 수정 `edit`

@@@7
 
  사용자의 수정된 정보를 업데이트합니다.
  - 입력: 수정할 사용자 정보
  - 결과: 수정 완료 시 확인 메시지 페이지로 이동

### 9. 비밀번호 찾기 `find-password`

@@@8

  - 사용자가 아이디, 이름, 이메일을 통해 임시 비밀번호를 요청.
  - 유효한 사용자 정보가 확인되면 임시 비밀번호가 생성되어 표시됩니다.
  - 입력: 아이디, 이름, 이메일
  - 결과: 임시 비밀번호 표시 페이지로 이동

### 10. 아이디 찾기 ‘find-id`

@@@9

  - 사용자가 이름과 이메일을 통해 자신의 아이디를 요청. 
  - 유효한 사용자 정보가 확인되면 아이디가 표시됩니다.
  - 입력: 이름, 이메일
  - 결과: 아이디 표시 페이지로 이동

## 로그 및 디버깅

`logger`를 사용하여 각 메서드의 입력값과 중요한 단계에서의 상태를 디버깅 로그로 출력.

