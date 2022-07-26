# 문자열 치환(replace) 사용법 & 예제

- String변수나 배열 같은 곳에 많은 양의 데이터들이 들어가 있을 경우 자신이 바꾸고자 하는 값만 골라서 바꾸기란 쉽지 않습니다. 
- 이럴 때 유용하게 쓰일 수 있는 함수가 바로 Replace함수입니다. 

## Replace
- String a = "무궁화 삼천리 화려강산 대한사람 대한으로 길이 보전하세 ";	 <br/>
//replace([기존문자],[바꿀문자]) <br/>
a= a.replace("대한", "민국");	<br/>
System.out.println(a); <br/><br/>

//결과값 : 무궁화 삼천리 화려강산 민국사람 민국으로 길이 보전하세 <br/><br/>

=> String replace(CharSequnce target, CharSequence replacement) <br/>
Replace 함수는 자신이 바꾸고싶은 문자로 문자열을 치환시켜주는 기능을 합니다. <br/><br/><br/>


## ReplaceALL
- String a = "무궁화 삼천리 화려강산 대한사람 대한으로 길이 보전하세 ";	 <br/>
//replaceAll([정규식],[바꿀문자]) <br/>
a= a.replaceAll("대한", "민국"); <br/>
System.out.println(a); <br/><br/>

//결과값 : 무궁화 삼천리 화려강산 민국사람 민국으로 길이 보전하세<br/><br/>

ReplaceAll 함수는 자신이 바꾸고싶은 문자로 문자열을 전부 치환시켜주는 기능을 합니다. <br/>
여기서 많은 분들은 Replace와 ReplaceAll과의 같은 것이 아니냐고 반문을 할 수도 있을 듯합니다. <br/>
실제로 나오는 결과물의 값이 같습니다. 하지만 차이점은 분명 있습니다. <br/>
Replace는 첫 번째 값으로 바꿀 문자열을 입력받는 대신 첫 번째 인자 값으로 정규식이 들어갑니다. <br/>
그래서 Replace는 특수문자로도 치환이 되는데 반하여 ReplaceAll은 특수문자로 치환이 어렵습니다.<br/><br/><br/>


### Replace와 ReplaceALL의 차이점
- String a = "무궁화. 삼천리. 화려강산. 대한사람. 대한으로. 길이. 보전하세 ";
//replace([기존문자],[바꿀문자]) <br/>
a = a.replace(".", "/"); <br/>
System.out.println(a); <br/><br/>

//결과값 : 무궁화/ 삼천리/ 화려강산/ 대한사람/ 대한으로/ 길이/ 보전하세 <br/><br/>

=> . 을 /로 치환할 경우 replace함수는. 을 /로 정상적으로 바꾸어주었지만  <br/>
SString a = "무궁화. 삼천리. 화려강산. 대한사람. 대한으로. 길이. 보전하세 "; <br/>
//replaceAll([정규식],[바꿀문자]) <br/>
a = a.replaceAll(".", "/"); <br/>
System.out.println(a); <br/><br/>

//결과값 : ///////////////////////////////////// <br/><br/>

replaceAll 같은 경우 문자열 전체가 치환되는 것을 확인할 수 있습니다. <br/>
.(마침표)가 정규식으로 모든 문자를 의미하기 때문에 나타난 현상입니다. <br/><br/><br/>


### ReplaceFirst
- String a = "무궁화 삼천리 화려강산 대한사람 대한으로 길이 보전하세 "; <br/>
//replaceFirst([기존문자],[바꿀문자]) <br/>
a= a.replaceFirst("대한", "민국"); <br/>
System.out.println(a); <br/><br/>
 
//결과값 : 무궁화 삼천리 화려강산 민국사람 대한으로 길이 보전하세 <br/><br/>

ReplaceFirst 함수는 자신이 바꾸고 싶은 문자열이 처음으로 해당할 때만 치환시켜주는 기능을 합니다. <br/>



===============================================
# String.replace()
- 문자열 내에서 특정 문자를 다른 문자로 치환할 때 사용한다.

## 문법(Syntax)
- str.replace(regexp|substr, newSubstr|function)

- 매개변수(Parameter)
    1. regexp|substr

- 정규식 객체 또는 문자열로 치환하기 위해 찾는 파라미터
    2. newString|function

- 첫 번째 파라미터를 대신할 문자열 또는 함수 <br/><br/>

replace() 함수를 사용하여 첫 번째 매개변수(regexp|substr)를 찾아서 <br/>
두 번째 매개변수(newString|function)로 치환한다.<br/><br/><br/>

let str = 'Hello Everyone'; <br/>
let newStr = str.replace('e', '2'); <br/>
console.log(str); // Hello Everyone <br/>
console.log(newStr); // He2llo Everyone <br/><br/>

* 문자열 str의 첫 번째 'e'가 '2'로 변경된 것을 확인할 수 있다.
* 원래 문자열은 변경되지 않는다.
let str = 'Hello Everyone'; <br/>
let newStr = str.replace(/e/g, '2'); <br/>
console.log(newStr); // H2llo Ev2ryon2 <br/><br/>

let newStr2 = str.replace(/e/gi, '2'); <br/>
console.log(newStr2); // H2llo 2v2ryon2 <br/>

* 정규식을 사용해서 치환도 가능하다.
* 정규식으로 사용하려는 문자열을 / 로 감싸서 들어가는 파라미터가 정규표현식임을 선언한다. <br/><br/>

정규식에서 g는 전체 문자열을 치환(global), <br/>
 i는 영문 대소문자를 무시하고 일치하는 패턴 검색하여 치환(ignore) 함수로 한번에 모두 치환하기 <br/><br/>

let str = 'Hello Everyone'; <br/>
function replaceAll(str, searchStr, replaceStr) { <br/>
  return str.split(searchStr).join(replaceStr); <br/>
} <br/>
let str2 = replaceAll(str, 'e', '2') <br/>
console.log(str2); // H2llo Ev2ryon2  <br/>