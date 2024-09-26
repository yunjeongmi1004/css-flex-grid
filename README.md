# 실무에서 주로 사용하는 Flex 와 Grid의 상세한 개념 정리를 위함

## Flex vs Grid

- TIP : flex/grid 공부할때 파이어폭스로 활용하면 편함
- 더 나중에 나온 스펙인 Grid로도 Flex와 똑같이 구현할 수 있는 경우가 많지만
- Grid로는 구현이 어려운 레이아웃이거나 Flex를 쓰는게 더 편리한 경우도 있음
- 둘 다 잘 알아두고 적재적소에 활용하는 것이 가장 좋다.



### Flex
- flex 부모 컨테이너 / flex item 으로 구성됨
- flex 부모 컨테이너에 선언하게 되면 flex item 들은 가로방향으로 배치되고, 자신이 가진 내용물의 width 만큼만 차지하게 된다. 
`display:flex;`



#### flex-direction : 아이템 배치 축의 방향을 결정하는 속성
`
.container{
    flex-direction: row; // 기본값
    flex-direction: column; // 세로정렬
    flex-direction: row-reverse; // 거꾸로 가로
    flex-direction: column-reverse; // 거꾸로 세로
}
`



#### flex-wrap : 아이템의 총합 보다 컨테이너가 더 작아졌을때 아이템의 줄넘기 처리 설정
`
.flex-container {
    display: flex; 
    flex-wrap: nowrap; // 기본값 삐져나감 (한줄처리)
    flex-wrap: wrap; // 아래로 다중 줄 처리
    flex-wrap: wrap-reverse; // 거꾸로 다중 줄 처리
}
`



#### flex-flow : flex-direction과 flex-wrap을 한번에 지정할 수 있는 단축속성

`
.flex-container{
    flex-flow:row wrap; // flex-direction:row + flex-wrap:wrap
}
`



### justify-content : 메인축 방향으로 아이템들을 정렬하는 속성
`
.flex-container{
    display: flex;
    justify-content: flex-start; // 기본값 메인축 방향 순서대로
    justify-content: flex-end; // 메인축 방향 반대
    justify-content: center; // 메인축 방향 가운데
    justify-content: space-between; // 메인축 양쪽 끝 중앙 정렬
    justify-content: space-around; // 메인축 중앙 간격 정렬
    justify-content: space-evenly;  // 모든 여백이 동일 (edge 에서 안됨)
}
`


### align-items : 수직축 방향 정렬
`
.flex-container {
    display: flex;
    align-items: stretch; // 기본 수직 쭉 늘려줌
    /* align-items: flex-start; */ // 수직 쭉 안늘려줌
    /* align-items: flex-end; */ // 아래 정렬 수직 안늘려줌
    /* align-items: center; */ // 중앙 정렬 수직 안늘려줌
    /* align-items: baseline; */ // 텍스트 베이스 라인으로 수직 정렬(안늘리고)
    height: 300px;
}
`


### align-content : 여러 행 정렬 , flex-wrap:wrap; 설정된 상태에서, 아이템들의 행이 2줄 이상 되었을 때의 수직축 방향 정렬을 결정하는 속성


