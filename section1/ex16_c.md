# 문자열, 배열 중복 제거 
1. new Set([iterable]); <br/><br/>

삽입 순서대로 요소 순회, Set에는 중복된 값이 들어올 수 없다. <br/>
const setTest = new Set(); <br/><br/>

setTest.add(1);	// {1} <br/>
setTest.add(2);	// {1, 2} <br/>
// 1을 add해도 set에 1이 있어서 무시됨 <br/>
setTest.add(1);	// {1, 2} <br/><br/>
 
arr.filter(callback(element[, index[, array]])[, thisArg]) <br/><br/>

callback : 요소를 걸러주는 함수, 조건에 맞지 않으면 삭제 <br/>
element : 처리할 현재 요소 <br/>
index(option) : 처리할 현재 요소의 인덱스 <br/>
const filterArr = [1, 2, 3, 4, 5]; <br/><br/>

filterArr.filter(function(v){ <br/>
	return v > 3;	// [4, 5] <br/>
}); <br/><br/>

// 화살표 함수 <br/>
filterArr.filter(v => v > 3);	// [4, 5] <br/><br/>
  
# 문자열, 배열 중복 제거하기  
- /* 문자열 중복 제거 : [...new Set(str)].join('') */ 
const str = 'abcaabbd'; <br/><br/>

// new Set으로 중복 제거 <br/>
new Set(str);			// {"a", "b", "c", "z"} <br/>
[...new Set(str)];		//  ["a", "b", "c", "z"] <br/>
[...new Set(str)].join('');	// "abcz" <br/>
// 기존 str이 영향받지 않는다. <br/>
console.log(str);		// "abcaabbd" <br/><br/><br/>


- /* 배열 중복 제거 : 1. [...new Set(arr)], 2. Array.prototype.filter() */ 
const arr = ['a', 'b', 'c', 'a', 'a', 'b', 'b', 'd']; <br/><br/>

// 1. [...new Set(arr)] <br/>
[...new Set(arr)]	// ["a", "b", "c", "d"] <br/>
// 기존 arr가 영향받지 않는다. <br/>
console.log(arr);	// ["a", "b", "c", "a", "a", "b", "b", "d"] <br/><br/>

// 2. Array.prototype.filter() <br/>
// indexOf는 처음으로 발견한 a의 index 위치만 반환하기 때문에, <br/>
// 그 다음에 a를 순회할때는 indexOf(v)와 i가 맞지 않는다. <br/>
arr.filter((v, i) => arr.indexOf(v) === i); // ["a", "b", "c", "d"] <br/>
// 기존 arr가 영향받지 않는다. <br/>
console.log(arr);	// ["a", "b", "c", "a", "a", "b", "b", "d"] <br/>

