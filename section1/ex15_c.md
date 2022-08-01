# .... 생각 과정
- 가운데를 찾기위해 나누기 2를 생각했다.
- 문자열이 짝수일 경우 나눈 몫이 0 이나 가운데 두글자를 뽑아내야 한다고 생각했다.
- 문자열이 홀수일 경우 나눈 몫 + 1 을 해야한다 생각했다. 
- Math.floor() 를 사용해야 한다고 생각했다.
- 원하는 부분만 잘라내기위해 substr()을 사용해야 한다고 생각했다.

# ..... 막힌 부분 
- substr() 을 쓰면서 시작부분만 쓰고 얼마나 뽑아낼지 길이를 쓰지 않았다. 
- 인덱스 번호가 0 부터 시작임을 잊고 middle 에 str.length / 2 만 하고 넘겼음.. 



# Math.floor() 함수
- 소수점을 버림하여 정수를 반환하는 함수입니다.
- Math의 객체를 사용하며, floor() 함수를 사용하게 되면 소수점 이하를 버려 나머지 정수를 반환하게 됩니다.
- Math.floor() 함수 사용방법 <br/><br/>

 => Math.floor( [ 변환 소수점 값 ] ); <br/><br/><br/>



# substr() : 특정 Index에서 원하는 길이만큼 잘라서 문자열로 리턴
- substr()의 Syntax는 아래와 같습니다. 
- start는 Index이며 이 Index부터 인자로 전달한 길이만큼 문자열을 잘라서 문자열로 리턴합니다. <br/><br/>

=> str.substr(start , length) <br/><br/>

- substr(5)처럼 start만 전달하면 start부터 문자열의 마지막까지 잘라서 리턴합니다. 
- substr(0, 5)는 Index 0부터 길이 5 만큼 문자열을 잘라 리턴합니다. <br/><br/>

let str = 'HelloWorldJavascript'; <br/><br/>

let a = str.substr(5); <br/>
let b = str.substr(0, 5); <br/>
let c = str.substr(0, 10); <br/><br/>

console.log(a); <br/>
console.log(b); <br/>
console.log(c); <br/><br/>

Output: <br/>
WorldJavascript <br/>
Hello <br/>
HelloWorld <br/>
