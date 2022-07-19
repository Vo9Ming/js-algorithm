# 다수의 최솟값 구하기

## 자바스크립트에서 Math.min() 함수를 사용하여 배열의 최소값 찾기.
- 주어진 배열에 존재하는 최소값을 찾으려면 <br/>
	JavaScript에서Math.min()함수를 사용할 수 있습니다.<br/> 
	이 함수는 주어진 배열에 존재하는 최소값을 반환합니다. <br/><br/>
	
	var myArray = [1, 5, 6, 2, 3];<br/>
	var m = Math.min(...myArray);<br/>
	console.log(m)<br/>
	출력: <br/>
	1 <br/>

- 출력에서 볼 수 있듯이 배열의 최소값은Math.min()함수에 의해 반환됩니다. <br/>
    일부 브라우저는 위의 방법을 지원하지 않을 수 있으므로 <br/>
    Math.min()함수와 함께 apply()함수를 사용하여 <br/>
    주어진 배열에서 최소값을 가져올 수 있습니다. <br/><br/>
    
    var myArray = [1, 5, 6, 2, 3]; <br/>
    var m = Math.min.apply(null, myArray); <br/>
	console.log(m) <br/>
	출력:<br/>
	1<br/>

 
### +@참고 
 ## JavaScript에서 Math.max() 함수를 사용하여 배열의 최대 값 찾기

- 주어진 배열에 존재하는 최대 값을 찾으려면 <br/>
JavaScript에서Math.max()함수를 사용할 수 있습니다. <br/>
이 함수는 주어진 배열에있는 최대 값을 반환합니다.<br/>
- 또한 apply()함수를 Math.max() 함수와 함께 사용하여 <br/>
주어진 배열에서 최대 값을 가져올 수 있습니다. <br/><br/>


### 참고 링크
Developer.mozilla.org


=========================================

# 배열 최소값, 최대값, 평균 구하는 방법

- 일반적인 프로그래밍 언어( C, C++, java)를 사용하여 <br/>
최소값, 최대값, 평균값을 구할 때는 반복문을 이용하여 구하는 경우가 많다. <br/><br/>

하지만 자바스크립트에서는 반복문을 이용하지 않고도 <br/>
빌트인 함수로 최대와 최소, 그리고 평균값을 구할 수 있습니다. <br/>

## 배열에서 최소값 

const array = [ 1 , 2 , 3 , 4 , 5 ];  <br/><br/><br/>

Math.min.apply(null , array); <br/><br/>

=> apply 함수의 첫번째 파라미터는 함수에 사용될 this 이고, <br/> 
두번째 인자는 원본 배열입니다. <br/>


## 배열에서 최대값

const array = [ 1 , 2 , 3 , 4 , 5 ]; <br/><br/><br/>

Math.max.apply( null , array ); <br/><br/>

배열의 최대값은 최소값을 구하는 것과 사용되는 빌트인 함수만 다릅니다. <br/>


## 배열의 평균 값

const average = arr = arr.reduce ( ( p , c ) ==> p + c , 0 ) /arr.length; <br/><br/>

const array = [ 1 , 2 , 3 , 4 , 5 ]; <br/>
average( array );<br/><br/><br/>

 => reduce 함수는 인자로 callback 함수와 초기값을 받음.<br/><br/>

 => callback 함수의 인자는 누산 저장될 변수 ( acc ), <br/>
 현재 값( cur ) , 현재 인덱스 ( idx ), 원본 배열( src ). <br/><br/><br/>

### +@ 배열의 평균을 구하기 위한 가장 간단한 방법은 
Array.prototype.reduce( ) 빌트인 함수를 이용하는 것입니다. <br/>
reduce 함수를 이용하면 배열 내의 모든 값의 합계를 구할 수 있고, <br/>
이를 배열의 길이러 나눠주기만 하면됩니다. <br/>

