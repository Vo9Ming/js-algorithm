# min = Number.MAX_SAFE_INTEGER;
- 최솟값을 구할때 가장 큰 값을 min 에 넣어서 
- 반복문을 진행하면 배열의 첫번째 수를 min 값에 넣고 시작한다.


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


# push( ) 메서드를 사용하여 JavaScript에서 배열의 요소 추가
- push()메소드는 배열 끝에 요소를 추가하는 데 사용됩니다. <br/>
단일 요소, ​​여러 요소 또는 배열을 추가 할 수 있습니다. <br/>
가장 간단하고 가장 빠른 옵션 중 하나이며, 경우에 따라 대형 배열에서Array.length를 사용하는 방법을 능가합니다. <br/>
push()에 의해 수행되는 작업은.pop()메서드로 되돌릴 수 있습니다. <br/>
여러 요소가 함께 전달되면 push()연산자에 의해 순서가 유지됩니다. <br/>
이 방법은 또한 배열을 변경하므로 변경됩니다.

- const arr =[1,2,3]; <br/>
const arr2 = [8,9,10]; <br/>
arr.push(4);// single item <br/>
arr.push(5,6,7);// multiple items <br/>
arr.push(...arr2);// spread operator <br/>
console.log(arr); <br/>

