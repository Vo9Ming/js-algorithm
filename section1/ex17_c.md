# 배열 중복 제거 
- 1.[...new Set(arr)], 
- 2.Array.prototype.filter()  <br/><br/>

const arr = ['a', 'b', 'c', 'a', 'a', 'b', 'b', 'd']; <br/><br/>

1. [...new Set(arr)] <br/>
[...new Set(arr)]	// ["a", "b", "c", "d"] <br/>
 기존 arr가 영향받지 않는다. <br/>
console.log(arr);	// ["a", "b", "c", "a", "a", "b", "b", "d"] <br/><br/>

2. Array.prototype.filter() <br/>
 indexOf는 처음으로 발견한 a의 index 위치만 반환하기 때문에, <br/>
 그 다음에 a를 순회할때는 indexOf(v)와 i가 맞지 않는다. <br/>
arr.filter((v, i) => arr.indexOf(v) === i); // ["a", "b", "c", "d"] <br/>
 기존 arr가 영향받지 않는다. <br/>
console.log(arr);	// ["a", "b", "c", "a", "a", "b", "b", "d"] <br/>
