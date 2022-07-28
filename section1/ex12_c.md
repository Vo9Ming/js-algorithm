
# String.prototype.toUpperCase()
- toUpperCase() 메서드는 문자열을 대문자로 변환해 반환합니다.

## 구문
 => str.toUpperCase()

## 반환 값
- 대문자로 변환한 새로운 문자열.

## 예외
- TypeError <br/>
    => Function.prototype.call() 등을 사용해 null이나 undefined에서 호출 시.

## 설명
- toUpperCase() 메서드는 문자열을 대문자로 변환한 값을 반환합니다. <br/>
JavaScript의 문자열은 불변하므로 원본 문자열에는 영향을 주지 않습니다. 


### 예제

- 기본 사용법 <br/>
console.log('alphabet'.toUpperCase()); // 'ALPHABET'<br/><br/><br/>


- 문자열이 아닌 this의 문자열 변환 <br/>
toUpperCase()의 this가 문자열이 아니고, undefined와 null도 아니면 자동으로 문자열로 변환합니다. <br/><br/>

const a = String.prototype.toUpperCase.call({ <br/>
  toString: function toString() { <br/>
    return 'abcdef'; <br/>
  } <br/>
}); <br/><br/>

const b = String.prototype.toUpperCase.call(true); <br/><br/>

// prints out 'ABCDEF TRUE'. <br/>
console.log(a, b); <br/>


=============================================

# String.prototype.toLowerCase()
- toLowerCase() 메서드는 문자열을 소문자로 변환해 반환합니다.
 
## 구문
    => str.toLowerCase()

## 반환값
- 호출 문자열을 소문자로 변환한 새로운 문자열

## 설명
- toLowerCase() 메서드는 호출 문자열을 소문자로 변환해 반환합니다.  <br/>
toLowerCase() 는 원래의 str에 영향을 주지 않습니다.


### 예제

 toLowerCase() <br/>
console.log('ALPHABET'.toLowerCase()); // 'alphabet' <br/>




