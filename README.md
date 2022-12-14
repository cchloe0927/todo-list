# [React] My Todo List
<hr>
항해99 주특기 입문 주차 과제
<br>
*예시 사이트 : http://todolistassignment.s3-website.ap-northeast-2.amazonaws.com/
<br>
*구현 사이트(배포) : https://todo-list-gamma-five.vercel.app/


## Constraints
1. 제목과 내용을 입력하고 [추가하기]버튼을 클릭하면 Working에 새로운 Todo가 추가되고 제목 input과 내용 input은 다시 빈 값으로 바뀌도록 구성해주세요.
2. Todo의 isDone 상태가 true이면, 상태 버튼의 라벨을 취소, isDone이 false 이면 라벨을 완료로 조건부 렌더링 해주세요.
3. Todo의 상태가 Working 이면 위쪽에 위치하고, Done이면 아래쪽에 위치하도록 구현합니다.
4. Layout의 최대 넓이는 1200px, 최소 넓이는 800px로 제한하고, 전체 화면의 가운데로 정렬해주세요.
5. 컴포넌트 구조는 자유롭게 구현해보세요.


## Table of Contents
- [구현 화면](#구현화면)
- [Components 구조](#Components구조)
- [UI 구성하기](#UI구성하기)
- [Todo 추가](#Todo추가)
- [Todo 삭제](#Todo삭제)
- [Todo 완료 상태변경 (완료 ↔ 진행중)](#Todo완료상태변경)

<hr>

## 구현화면

https://user-images.githubusercontent.com/96729804/204094697-5df18463-a560-4590-88b6-ae715f13b55b.mov

| 구현 영상(모니터화면) | 반응형 |
|:------:|:------:|
| <img width="1242" alt="스크린샷 2022-11-27 오전 11 54 37" src="https://user-images.githubusercontent.com/96729804/204117181-215571c6-66f8-424d-aa95-bf00beae647f.png"> | ![ezgif com-gif-maker](https://user-images.githubusercontent.com/96729804/204117316-1fe3270c-2908-4f38-9f8f-f39c7749e7b9.gif) |


## Components구조
<b>Header / Todo 추가 / Todo List가 보여지는 부분 / 각 해당 Todo</b>

| 컴포넌트 구조 시각화 |
|:------:|
| <img src="https://user-images.githubusercontent.com/96729804/204087464-12c657d0-06ff-4550-983a-26b87bcb2cf3.jpeg" width="650" height="350"/> |


> Header ① : 값이 변하지 않는 고정 부분이라 고유 컴포넌트로 분리함

> Todo 추가 ② : 새로운 todo-list를 추가하는 부분으로 추가 데이터만 전달하는 기능이기 때문에 데이터를 추가하는 부분의 컴포넌트로 분리함

> Todo List가 보여이는 부분 ③ : 모든 데이터를 받아서 핸드링 하는 부분으로 컴포넌트를 분리함

> 각 해당 Todo ④ : 각각의 Todo의 형태가 반복되기 때문에 하나의 컴포넌트로 분리함


## UI구성하기
<b>Header / Todo 추가 / Todo List가 보여지는 부분으로 나눔 (Components구조 거의 유사)</b>

> flex : grid와 달리 고정되었는 부분은 flex를 사용

> grid : todo리스트들이 보여지는 곳에서 working / Done으로 구분하고 각각 안에서 카드들이 추가될 때 다시 grid로 Layout 구현

> 반응형 - Media Query


## Todo추가
<b>1. Todo-list추가하기 및 추가한 후에 빈 값 처리하기</b>

> App - AddContents 컴포넌트

> App - Contents 컴포넌트

AddContents 컴포넌트에서 추가하기 버튼을 누르면 title, contens의 value를 App 컴포넌트에서 prop로 전달받은 함수를 호출하면서 인수로 전달해주고
Add 컴포넌트에서는 전달받은 매개변수를 핸드링해서 다시 Contents 컴포넌트로 데이터를 전달함

<b>2. 빈 값일 때 버튼 클릭 시, alert창 대신 CSS를 사용해 UI구성</b>


## Todo삭제
Todo List 추가시 고유 id값을 지정해서 객체안에 생성해주고 고유 id값을 비교해서 삭제기능 구현



## Todo완료상태변경
완료, 취소 버튼에 인수로 각 Todo-list의 고유 id값과 진행상태(progress)를 넘겨주고 App 컴포넌트에서 조건에 따라 state상태를 변경시켜준 데이터를 다시 전달함
완료 버튼 클릭 시, Done 칸으로 이동하고 취소 버튼을 클릭 시, Working 칸으로 이동


