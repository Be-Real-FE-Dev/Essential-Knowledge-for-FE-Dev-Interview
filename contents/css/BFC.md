# BFC(Block Formatting Context)

- 블록 서식 맥락
  블록 서식 맥락(block format context)은 웹 페이지를 렌더링하는 시각적 CSS의 일부로서, 블록 박스의 레이아웃이 발생하는 지점과 플로팅 요소의 상호작용 범위를 결정하는 범위입니다.
- bfc에서 박스들은 자신의 컨테이닝 블록의 상단부터 시작해서 수직으로 배치되고, ifc에서는 수평으로 배치

<br>

### 생성 조건

- float (float가 none이 아닌 요소)
- 절대 위치를 지정한 요소(position이 absolute 혹은 fixed인 요소)
- display 값이 table-cell, table-caption, inline-block, flex, inline-flex인 경우
- overflow (overflow가 visible이 아닌 요소)

<br>

### 활용

BFC는 마진 겹침현상을 방지한다.
float 된 요소들을 부모 컨테이너 안으로 들여 놓는다.
float된 요소를 글자들이 감싸는 것을 분리 한다.

[mdn-블록서식맥락](https://developer.mozilla.org/ko/docs/Web/Guide/CSS/Block_formatting_context)
