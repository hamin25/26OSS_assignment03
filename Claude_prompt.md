나는 HTML과 CSS를 공부하고 있는 초보 대학생이야.

이번 웹프로그래밍 과제로 "성적 관리 프로그램" CRUD Frontend Service를 만들려고 해.

아직 HTML, CSS, JavaScript를 배우는 단계이기 때문에
코드를 최대한 단순하고 이해하기 쉽게 작성해줘.

이번 과제에서는 Bootstrap을 사용할 거야.
따라서 Bootstrap 5를 사용해서 기본적인 디자인과 반응형 레이아웃을 구현해줘.

하지만 Bootstrap 클래스만 잔뜩 사용하는 복잡한 코드는 원하지 않아.
HTML의 기본 구조와 CSS의 역할을 내가 공부할 수 있도록
Bootstrap과 직접 작성한 CSS를 적절히 나누어서 사용해줘.

====================================
[사용 기술]
====================================

HTML
CSS
기초 JavaScript
Bootstrap 5

사용하지 말 것:
- React
- Vue
- TypeScript
- jQuery
- 기타 JavaScript 라이브러리
- 서버
- 데이터베이스
- localStorage

이번 과제는 Frontend 화면 구현이 목적이므로
실제로 데이터를 저장하는 기능은 구현하지 않아도 된다.

Bootstrap은 CDN 방식으로 연결해줘.

각 HTML 파일의 <head> 부분에 Bootstrap CSS를 연결하고,
필요하다면 body 마지막 부분에 Bootstrap JavaScript Bundle을 연결해줘.

====================================
[프로그램 주제]
====================================

성적 관리 프로그램

학생이 자신의 수강 과목과 성적 정보를 관리할 수 있는
간단한 CRUD Frontend Service이다.

데이터 Field는 총 7개로 구성한다.

1. 번호(id)
2. 과목명(subject)
3. 교수님(professor)
4. 전공/교양(category)
5. 학점수(credit)
6. GRADE/PF(gradeType)
7. 수강 학기(semester)

예시 데이터:

1 / 웹프로그래밍 / 홍길동 / 전공 / 3 / GRADE / 2026-2
2 / 자료구조 / 김교수 / 전공 / 3 / GRADE / 2026-1
3 / 대학영어 / 이교수 / 교양 / 2 / GRADE / 2026-1
4 / 컴퓨터개론 / 박교수 / 전공 / 3 / PF / 2025-2
5 / 심리학개론 / 최교수 / 교양 / 2 / GRADE / 2025-2
6 / 데이터베이스 / 정교수 / 전공 / 3 / GRADE / 2026-2

====================================
[파일 구조]
====================================

다음 5개의 파일을 만들어줘.

index.html
add.html
view.html
edit.html
my.css

별도의 JavaScript 파일은 만들지 말고,
필요한 JavaScript는 각 HTML 파일의 <script> 안에 작성해줘.

====================================
[1. index.html - 목록 페이지]
====================================

성적 관리 프로그램의 메인 페이지를 만들어줘.

상단에는 Bootstrap Navbar를 이용해서 Navigation을 만들어줘.

Navbar에는 다음 내용이 있으면 좋겠다.

"성적 관리"

그리고
"성적 목록"
"성적 추가"

메인 제목:

"성적 관리 프로그램"

간단한 설명:

"수강 과목과 성적을 한눈에 관리하세요."

성적 데이터를 Bootstrap의 table을 사용해서 보여줘.

다음 Field를 목록에 표시해줘.

번호 / 과목명 / 교수님 / 전공·교양 / 학점 / GRADE·PF / 학기

Bootstrap의 다음과 같은 Table 관련 클래스를 적절히 사용해줘.

table
table-striped
table-hover
table-bordered

각 과목의 과목명을 클릭하면 view.html로 이동하도록 만들어줘.

예:

<a href="view.html">웹프로그래밍</a>

페이지에 Bootstrap Button을 이용하여

"+ 과목 추가"

버튼을 만들어줘.

버튼을 클릭하면 add.html로 이동하도록 해줘.

Vercel 기본 URL에 접속했을 때
index.html이 바로 표시되어야 한다.

====================================
[2. add.html - 추가 페이지]
====================================

새로운 성적 정보를 입력하는 Form 페이지를 만들어줘.

페이지 제목:

"성적 추가"

Bootstrap의 form-control, form-select, btn 등의 클래스를 사용해줘.

다음 7개 Field를 모두 포함해줘.

1. 번호
→ input type="number"

2. 과목명
→ input type="text"

3. 교수님
→ input type="text"

4. 전공/교양
→ select

5. 학점수
→ select

6. GRADE/PF
→ select

7. 수강 학기
→ select

전공/교양:

- 전공
- 교양

학점:

- 1
- 2
- 3
- 4

GRADE/PF:

- GRADE
- PF

수강 학기:

- 2025-1
- 2025-2
- 2026-1
- 2026-2

각 input에는 label을 사용해줘.

필수 입력 항목에는 required를 사용해줘.

Bootstrap의 form-control과 form-select를 활용해줘.

Form은 Bootstrap Grid를 활용해서
Desktop에서는 2열 정도로 보이고,
Mobile에서는 1열로 보이도록 만들어줘.

예를 들어:

<div class="row">
    <div class="col-md-6">
        ...
    </div>

    <div class="col-md-6">
        ...
    </div>
</div>

JavaScript Validation을 최소 4개 적용해줘.

예:

1. 과목명이 비어 있는지 확인
2. 교수님이 비어 있는지 확인
3. 학점이 올바른지 확인
4. 전공/교양이 선택되었는지 확인
5. 수강 학기가 선택되었는지 확인

Validation에 실패하면 alert()로 알려줘.

모든 입력이 정상이라면

confirm("과목이 추가됩니다.")

를 사용해줘.

확인을 누르면

alert("과목이 추가되었습니다.")

를 보여줘.

실제로 데이터를 저장하지 않아도 된다.

====================================
[3. view.html - 상세 페이지]
====================================

index.html에서 특정 과목을 클릭했을 때 이동하는
상세 정보 페이지를 만들어줘.

페이지 제목:

"성적 상세 정보"

임의의 Record 하나를 보여줘.

예:

번호: 1
과목명: 웹프로그래밍
교수님: 홍길동
전공/교양: 전공
학점수: 3
GRADE/PF: GRADE
수강 학기: 2026-2

7개의 Field를 모두 표시해야 한다.

Bootstrap Card를 사용해서
깔끔하게 보여줘.

예:

card
card-header
card-body

등을 적절히 사용해줘.

아래에 다음 버튼을 만들어줘.

[수정]
→ edit.html로 이동

[삭제]
→ confirm() 사용

confirm 메시지:

"이 과목을 삭제하시겠습니까?"

[목록으로]
→ index.html로 이동

실제 데이터를 삭제하지 않아도 된다.

====================================
[4. edit.html - 수정 페이지]
====================================

기존 성적 정보를 수정하는 Form 페이지를 만들어줘.

페이지 제목:

"성적 수정"

add.html과 비슷한 Form을 사용해줘.

하지만 기존 Record의 값이 이미 입력되어 있어야 한다.

예:

번호: 1
과목명: 웹프로그래밍
교수님: 홍길동
전공/교양: 전공
학점수: 3
GRADE/PF: GRADE
수강 학기: 2026-2

input에는 value를 사용하고,
select에는 selected를 사용해서
기존 값이 Form에 표시되도록 해줘.

7개의 Field를 모두 수정할 수 있도록 해줘.

Bootstrap Grid를 사용해서

Desktop:
2열

Mobile:
1열

로 보이도록 해줘.

Validation을 최소 4개 적용해줘.

예:

- 과목명 필수
- 교수님 필수
- 학점 확인
- 전공/교양 선택 확인
- 학기 선택 확인

[수정] 버튼을 클릭하면

confirm("이 과목을 수정할까요?")

를 보여줘.

확인을 누르면

alert("수정되었습니다.")

를 보여줘.

실제로 데이터를 수정할 필요는 없다.

====================================
[5. my.css - 공통 CSS]
====================================

모든 HTML 페이지에서 동일한 my.css를 연결해줘.

Bootstrap이 기본적인 디자인을 담당하고,
my.css에서는 내가 직접 작성한 CSS가 보이도록 해줘.

다음 부분에 간단한 CSS를 직접 작성해줘.

- body
- Header 또는 페이지 제목
- Card
- Table
- Button
- Footer
- Navigation과 관련된 간단한 부분

단, Bootstrap의 기본 스타일을 지나치게 덮어쓰지는 말아줘.

CSS는 초보자가 이해할 수 있도록 간단하게 작성해줘.

예를 들어:

body {
    background-color: ...;
}

.page-title {
    margin-top: ...;
    margin-bottom: ...;
}

처럼 기본적인 CSS 속성을 사용해줘.

====================================
[6. Responsive Web Design]
====================================

이번 과제에서는 Desktop과 Phone 환경을 모두 지원해야 한다.

Bootstrap의 Responsive Grid를 적극적으로 사용해줘.

예:

col-md-6
col-lg-4
container
row

등을 활용해줘.

Desktop에서는 Form이 2열로 보이고,
Mobile에서는 1열로 보이게 해줘.

Table은 Mobile 화면에서 화면 밖으로 넘어가지 않도록

<div class="table-responsive">

를 사용해줘.

Navbar도 Bootstrap의 responsive navbar를 사용해서
Mobile 화면에서 정상적으로 사용할 수 있도록 해줘.

별도의 복잡한 Media Query는 최대한 사용하지 않아도 된다.
Bootstrap의 Responsive 기능을 우선적으로 활용해줘.

다만 과제에서 CSS Media Query를 사용한 부분도 보여주고 싶다면
my.css에 아주 간단한 Media Query 하나 정도만 추가해줘.

====================================
[디자인]
====================================

전체적으로 깔끔한 대학생 과제 느낌으로 만들어줘.

너무 화려한 애니메이션이나 복잡한 디자인은 사용하지 말 것.

색상도 너무 많이 사용하지 말고
Bootstrap의 기본적인 색상 체계를 활용해줘.

예:

primary
secondary
success
danger
warning

등을 적절히 사용해줘.

====================================
[초보자를 위한 코드 작성 규칙]
====================================

나는 HTML/CSS 초보자이기 때문에
코드를 최대한 이해하기 쉽게 작성해줘.

다음 원칙을 지켜줘.

1. 코드를 지나치게 짧게 만들지 말 것.
2. 한 줄에 너무 많은 작업을 넣지 말 것.
3. JavaScript는 if문, function, alert(), confirm() 정도의 기초적인 문법을 사용할 것.
4. 복잡한 JavaScript 문법은 사용하지 말 것.
5. HTML 구조를 명확하게 보여줄 것.
6. Bootstrap 클래스를 사용한 부분에는 간단한 주석을 달아줄 것.
7. 중요한 HTML 요소에는 한국어 주석을 달아줄 것.
8. CSS에도 중요한 부분에는 한국어 주석을 달아줄 것.

====================================
[코드를 만든 후 설명]
====================================

코드를 보여주기 전에 먼저 전체 파일 구조를 설명해줘.

예:

index.html
→ 성적 목록

add.html
→ 성적 추가

view.html
→ 성적 상세보기

edit.html
→ 성적 수정

my.css
→ 공통 디자인

그리고 각 페이지의 코드를 보여준 후,
초보자가 이해할 수 있도록 주요 부분을 설명해줘.

특히 다음 개념이 실제 코드에서 어디에 사용되었는지 설명해줘.

HTML:
- table
- form
- input
- select
- option
- button
- a
- label
- class
- id

CSS:
- margin
- padding
- width
- background-color
- border
- Media Query

Bootstrap:
- container
- row
- col-md-6
- table
- table-responsive
- form-control
- form-select
- btn
- navbar
- card

JavaScript:
- function
- if
- required
- alert()
- confirm()

마지막에는 과제 요구사항 체크리스트를 만들어줘.

☑ 6개 이상의 Field
☑ index.html
☑ add.html
☑ view.html
☑ edit.html
☑ my.css
☑ List Page
☑ Add 버튼
☑ 상세보기 링크
☑ 6개 이상의 목록 Field
☑ 6개 이상의 Form Field
☑ required
☑ JavaScript Validation 4개 이상
☑ alert()
☑ confirm()
☑ Edit 버튼
☑ Delete 기능의 confirm()
☑ Bootstrap
☑ Responsive Web Design
☑ Desktop 화면
☑ Mobile 화면
☑ Vercel에서 index.html 표시

마지막으로 "이 코드에서 내가 직접 공부하면 좋은 부분"도
5개 정도 골라서 알려줘.

가장 중요한 것은 완성도 높은 복잡한 웹사이트를 만드는 것이 아니라,
HTML/CSS를 배우는 학생인 내가 코드를 읽고 이해할 수 있는 수준으로 만드는 것이다.