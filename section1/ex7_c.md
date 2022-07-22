# for .... of 
- for...of 명령문은 <br/>
반복 가능한 객체 (Array, Map, Set, String, TypedArray, arguments 객체 등을 포함)에 대해서 <br/>
반복하고 각 개별 속성값에 대해 실행되는 문이 있는 사용자 정의 반복 후크를 호출하는 루프를 생성합니다.


## 구문 

for (variable of iterable) {   <br/>
  statement  <br/>
} <br/><br/>

- variable <br/>
    각 반복에 서로 다른 속성값이 variable에 할당됩니다. <br/>
- iterable <br/>
    반복되는 열거가능(enumerable)한 속성이 있는 객체. <br/>