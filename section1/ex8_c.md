
# 배열의 합계, 평균 계산하기  - reduce(), reduceRight()

- 배열의 내장객체인 reduce() 함수는 <br/>
배열의 element들을 처리하여 하나의 값을 도출해 내는 함수입니다. <br/>
 
- 여러가지 다양한 방법으로 이 함수를 활용할 수 있지만, <br/>
reduce() 함수를 이용하여
배열 element들의 합계와 평균을 계산하는 방법을 알아보도록 하자.

1. reduce()
2. reduce() 함수로 배열의 합계 구하기
3. reduce() 함수로 배열의 평균 구하기
4. reduceRight()


# 1. reduce()
	=> arr.reduce(callback(accumulator, currentValue [, currentIndex[, array]]) [, initialValue]);
 
- reduce() 함수는... 
배열(arr)의 각 element들에 대해서 <br/>
파라미터로 입력받은 callback 함수를 실행하여,
하나의 리턴값을 반환하는 함수입니다.
- callback 함수는 배열(arr)의 모든 element를 대상으로 한번씩 호출됩니다.
- 이 때, callback 함수에서 리턴되는 값은, <br/>
다음 element에 대한 callback 함수 실행시 파라미터(accumulator)로 입력되어 활용될 수 있습니다.
- 배열의 모든 element들에 대해 callback 함수 실행이 완료되면, <br/>
reduce() 함수는 마지막 element의 callback 함수의 리턴값을 리턴합니다. 
- 따라서, reduce() 함수를 사용하면, 배열을 순차적으로 순회하면서 배열의 값을 누적하는데 유용합니다.
 
### 파라미터 
- callback 함수 <br/>
배열의 각 element들에 대해서 실행되는 callback 함수이고, <br/> 
이 함수의 리턴값은 다음 element에 대한 callback 함수 실행시 파라미터(accumulator)로 전달됩니다. <br/><br/>

* accumulator : 이전 element에 대한 callback 함수의 리턴값
* currentValue : 현재 처리중인 배열 element
* currentIndex : 현재 처리중인 배열 index
* array : 배열 전체

 
- initialValue <br/>
callback 함수를 처음 실행할 때, accumulator의 값. <br/><br/>
 
initialValue를 지정하지 않으면, <br/>
callback 함수를 처음 실행할 때, <br/>
accumulator의 값은 배열의 첫번째 값(arr[0])이 되고, <br/>
currentIndex는 1이 됩니다. <br/><br/>
 
initialValue를 지정하면, <br/>
callback 함수를 처음 실행할 때,  <br/>
accumulator의 값은 initalValue가 되고, <br/>
currentIndex는 0이 됩니다. <br/><br/>

리턴값  <br/>
최종 누적 값(accumulator) <br/><br/><br/>

======================================================================

2. reduce() 함수로 배열의 합계 구하기
 
### 예시

const arr = [1, 2, 3]; <br/><br/>

const result = arr.reduce(function add(sum, currValue) { <br/>
  return sum + currValue; <br/>
}, 0); <br/><br/>

document.writeln(result); // 6 <br/><br/>

reduce() 함수를 사용하여 배열의 합계를 구했습니다. <br/>
reduce() 함수의 파라미터로 전달되는 callback 함수는 <br/>
누적값(sum), 현재 처리중인 배열의 element(currValue)를 파라미터로 받습니다. <br/>
그리고, 누적값과 currValue의 합을 리턴하면, <br/>
배열의 다음값을 처리할 때, 이 리턴된 값이 callback 함수의 누적값(sum)으로 전달됩니다. <br/>
초기값은 0으로 지정하였습니다. <br/><br/><br/>
 

!!! 가능하면 초기값을 반드시 지정하세요. <br/>
reduce() 함수의 두 번째 파라미터인 initialValue는 필수값이 아니지만, <br/>
가능하면 반드시 입력하는 것이 좋습니다.<br/><br/><br/><br/>

const arr = [];<br/><br/>

// error<br/>
const result = arr.reduce(function add(sum, currValue) { <br/>
  return sum + currValue; <br/>
}); <br/>

document.writeln(result);  <br/><br/>

reduce() 함수의 초기값이 지정되지 않으면, <br/> 
reduce() 함수는, 배열의 첫번째 값을 처리할 때 <br/>
accumulator(위 예제에서는 sum) 값으로 배열의 첫번째 값(arr[0])을 세팅합니다. <br/>
그런데, 위 예제의 케이스에는 빈 배열이 전달되었으므로, arr[0]은 잘못된 접근이기 때문에, 에러가 발생합니다.  <br/><br/>

만약 같은 경우에, 초기값(initialValue)을 지정하면, <br/>
reduce() 함수는, 배열의 첫번째 값을 처리할 때 <br/>
 accumulator(위 예제에서는 sum) 값으로 initialValue를 지정하기 때문에 에러가 발생하지 않습니다. <br/>

==================================================================================

3. reduce() 함수로 배열의 평균 구하기 <br/><br/><br/>

const arr = [1, 2, 3];<br/><br/>

const result = arr.reduce(function add(sum, currValue) { <br/>
  return sum + currValue; <br/>
}, 0); <br/>
const average = result / arr.length; <br/><br/>

document.writeln(average); // 2 <br/><br/>

reduce() 함수를 사용하여 배열 element의 합을 구하고, <br/> 
그 결과를 배열의 길이로 나누어서 배열 element의 평균값을 계산하였습니다. <br/>

==================================================================================


## reduceRight() 
=> arr.reduceRight(callback(accumulator, currentValue [, currentIndex[, array]]) [, <br/> initialValue]) <br/><br/>
reduceRight() 함수는 reduce() 함수와 기능은 동일하고, 배열의 오른쪽부터 연산을 수행합니다.<br/><br/><br/>

const arr = ['a', 'b', 'c']; <br/><br/>

const result = arr.reduceRight(function (str, currValue) { <br/>
  return str + currValue; <br/>
}, ''); <br/><br/>

document.writeln(result); // cba <br/><br/>

reduceRight() 함수를 사용하여 배열의 끝에서부터 앞까지의 <br/>
문자열 element를 이어붙였습니다. <br/><br/><br/>

출처: https://hianna.tistory.com/408 [어제 오늘 내일:티스토리]





# Array.prototype.splice()
- splice() 메서드는 배열의 기존 요소를 삭제 또는 교체하거나 새 요소를 추가하여 배열의 내용을 변경합니다.

## 구문
    => array.splice(start[, deleteCount[, item1[, item2[, ...]]]])

### 매개변수
#### start
배열의 변경을 시작할 인덱스입니다. 배열의 길이보다 큰 값이라면 실제 시작 인덱스는 배열의 길이로 설정됩니다. <br/> 음수인 경우 배열의 끝에서부터 요소를 세어나갑니다(원점 -1, 즉 -n이면 요소 끝의 n번째 요소를 가리키며 <br/> array.length - n번째 인덱스와 같음). 값의 절대값이 배열의 길이 보다 큰 경우 0으로 설정됩니다. <br/>

#### deleteCount Optional
배열에서 제거할 요소의 수입니다.
- deleteCount를 생략하거나 값이 array.length - start보다 크면 start부터의 모든 요소를 제거합니다.
- deleteCount가 0 이하라면 어떤 요소도 제거하지 않습니다. 이 때는 최소한 하나의 새로운 요소를 지정해야 합니다.

#### item1, item2, ... Optional
배열에 추가할 요소입니다. 아무 요소도 지정하지 않으면 splice()는 요소를 제거하기만 합니다.

### 반환 값
- 제거한 요소를 담은 배열. 하나의 요소만 제거한 경우 길이가 1인 배열을 반환합니다. 
- 아무 값도 제거하지 않았으면 빈 배열을 반환합니다.

### 설명
- 만약 제거할 요소의 수와 추가할 요소의 수가 다른 경우 배열의 길이는 달라집니다.

##### 예제
- 하나도 제거하지 않고, 2번 인덱스에 "drum" 추가  <br/>
var myFish = ['angel', 'clown', 'mandarin', 'sturgeon']; <br/>
var removed = myFish.splice(2, 0, 'drum'); <br/><br/>

// myFish is ["angel", "clown", "drum", "mandarin", "sturgeon"] <br/>
// removed is [], no elements removed <br/>


- 하나도 제거하지 않고, 2번 인덱스에 "drum"과 "guitar" 추가 <br/>
var myFish = ['angel', 'clown', 'mandarin', 'sturgeon']; <br/>
var removed = myFish.splice(2, 0, 'drum', 'guitar'); <br/><br/>

// myFish is ["angel", "clown", "drum", "guitar", "mandarin", "sturgeon"]<br/>
// removed is [], no elements removed

- 3번 인덱스에서 한 개 요소 제거 <br/>
var myFish = ['angel', 'clown', 'drum', 'mandarin', 'sturgeon'];<br/>
var removed = myFish.splice(3, 1);<br/><br/>

// removed is ["mandarin"] <br/>
// myFish is ["angel", "clown", "drum", "sturgeon"] <br/>

- 2번 인덱스에서 한 개 요소 제거하고 "trumpet" 추가 <br/>
var myFish = ['angel', 'clown', 'drum', 'sturgeon']; <br/>
var removed = myFish.splice(2, 1, 'trumpet'); <br/><br/>

// myFish is ["angel", "clown", "trumpet", "sturgeon"] <br/>
// removed is ["drum"] <br/>

- 0번 인덱스에서 두 개 요소 제거하고 "parrot", "anemone", "blue" 추가 <br/>
var myFish = ['angel', 'clown', 'trumpet', 'sturgeon']; <br/>
var removed = myFish.splice(0, 2, 'parrot', 'anemone', 'blue'); <br/><br/>

// myFish is ["parrot", "anemone", "blue", "trumpet", "sturgeon"] <br/>
// removed is ["angel", "clown"] <br/>

- 2번 인덱스에서 두 개 요소 제거 <br/>
var myFish = ['parrot', 'anemone', 'blue', 'trumpet', 'sturgeon']; <br/>
var removed = myFish.splice(myFish.length - 3, 2); <br/><br/>

// myFish is ["parrot", "anemone", "sturgeon"] <br/>
// removed is ["blue", "trumpet"] <br/>

- 2번 인덱스에서 한 개 요소 제거 <br/>
var myFish = ['angel', 'clown', 'mandarin', 'sturgeon']; <br/>
var removed = myFish.splice(-2, 1); <br/><br/>

// myFish is ["angel", "clown", "sturgeon"] <br/>
// removed is ["mandarin"] <br/>

- 2번 인덱스를 포함해서 이후의 모든 요소 제거 <br/>
var myFish = ['angel', 'clown', 'mandarin', 'sturgeon']; <br/>
var removed = myFish.splice(2); <br/><br/>
 
// myFish is ["angel", "clown"] <br/>
// removed is ["mandarin", "sturgeon"] <br/>