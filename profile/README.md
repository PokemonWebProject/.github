# UserFlow 작성
Client가 웹 사이트 방문 시 흐름도 작성
![설계도](https://github.com/GroupStudy502/Project_WebPage/assets/127836690/0fdfd1f9-4303-4f70-93a3-33451b731017)


# 기능 명세서

## 🎇 회원

### ✅ 공통

- 권한

  - ADMIN / MEMBER 인가.
  - 가입 시 일반 회원(Member)

### ✅ 로그인

- 이메일 : 회원 정보 조회
- 로그인 : 이메일과 비밀번호 일치 조회
- 이메일 기억하기(세션에 회원 정보 유지) : 일주일 동안 유지(쿠키)

### ✅ 회원가입

- 비밀번호는 암호화(hashing) 과정을 거쳐 DB에 저장.
- DB에 영구 저장 처리
- 이메일 : 이메일 형식으로 입력, 이미 가입된 이메일인지 확인
- 비밀번호 : 8자리 이상 입력
- 비밀번호 확인: 비밀번호와 비밀번호 확인의 일치 여부
- 회원명 : 회원명 입력
- 약관 동의 : 약관 동의 확인 여부
- 다시 입력 : 입력한 회원 정보 칸 안에서 삭제
- 가입하기 : 입력한 회원 정보로 회원가입

## 🎇 메인 페이지

### ✅ 상단 우측
- 회원가입 -> 회원가입 페이지 이동
- 로그인 -> 로그인 페이지 이동
  - 로그인 이후 프로필 표시 및 마이페이지 & 로그아웃 표시
  - 관리자 로그인이면 사이트 관리 텍스트까지 표시

### ✅ 메뉴 베너

- 자유게시판 페이지로 이동
- 포켓몬 도감 조회 페이지로 이동
- 포켓몬 게임 링크 페이지로 이동

### ✅ 메인 페이지

- 포켓몬 뽑기
  - **뽑기 로직 구성안**
    1. 메인 웹페이지에서 뽑기 버튼 클릭
    2. 포켓몬DB에서 랜덤하게 포켓몬 데이터 Select
    3. Select된 데이터 이미지와 기본 정보 팝업 창에 표시
    4. 표시된 데이터를 회원 프로필 이미지로 설정할 수 있도록 셋업

### ✅ 메인 하단

- 하단 위쪽 개발자 팀 깃허브 주소와 개발자들의 깃허브 주소로 이동
- 중앙에 웹사이트 개발자들 관련 내용과 웹사이트 설명 간략히 삽입
- SNS 이미지를 누르면 포켓몬 SNS 주소로 이동

## 🎇 마이페이지
- 나의 프로필
    - 띠부씰 뽑기 혹은 나의 띠부씰에서 설정한 프로필 이미지 조회
- 나의 띠부씰
    - DB(MY_POKEMON 테이블)에 저장된 포켓몬 목록(띠부씰 뽑기 결과) 조회
    - 프로필 이미지로 변경, 선택삭제, 전체삭제 기능
- 회원정보 수정
    - DB(MEMBER 테이블)에 저장된 회원정보(이메일, 비밀번호, 비밀번호 확인, 이름, 회원 구분) 조회
    - 회원명 및 비밀번호 수정 기능

## 🎇 자유게시판

### ✅ 게시글

- [글쓰기]로 게시글 작성
- 로그인한 사용자만 글쓰기, 글수정, 글삭제 가능함
- 본문은 WYSIWYG(What You See Is What You Get, "보는 대로 얻는다") CKeditor 사용
- 게시글 제목 또는 작성자, 본문에 포함된 키워드로 조회.
- 글목록은 글10 개씩 목록 보여주며 하단에 페이지네이션 기능
- 게시글에 파일 첨부 가능함 (업로드 위치는 D:\uploads\ )

### ✅ 파일 업로드 & 다운로드

- 게시글에 파일 업로드하여 첨부 가능하도록 구현
- 첨부파일을 다운로드 받을 수 있도록 구현

## 🎇 포켓몬 도감 페이지

### ✅ 도감 조회

- 포켓몬 api 적용
- 검색으로 포켓몬 조회.
- 페이징
- https://www.pokemonkorea.co.kr/pokedex 참조

## 🎇 관리자 페이지
- 사이트 관리 아이콘 : 관리자 로그인 시 보이도록 설정

### ✅ 회원 관리

- 회원 목록 조회

  1.검색어별 조회
  -이메일
  -회원명
  -검색 키워드
  -사용자타입(전체 /일반사용자 / 관리자)

- 회원 수정 / 삭제
  - 수정, 삭제 가능한 부분을 ( 이름 / 사용자타입 ) 으로 제한

### ✅ 게시판 관리

- 게시글 전체 리스트 조회
  - 게시글 수정
  - 게시글 삭제

# ERD 작성
엔티티 관계도
![POKEMON PROJECT](https://github.com/GroupStudy502/Project_WebPage/assets/127836690/ec49efe9-2c15-40da-ada2-ed5ce5918a65)

# 역할 분담
- 이영태 : 포켓몬 도감 페이지
- 최혜진 : 자유 게시판 페이지
- 전수민 : 관리자 페이지
- 김재은 : 마이 페이지
- 이민혁 : 메인 페이지
- 조정인 : 로그인, 회원가입 페이지

