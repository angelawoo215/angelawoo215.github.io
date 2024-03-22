---
layout: single
title:  "[Javascript] Early return pattern"
tags:  강의 체험단 1기,  인프런 강의 추천, 자바스크립트 강의 추천, 자바스크립트 강의 
---

# TIL : Early return pattern
Early return pattern 사용해야 하는 이유
 if 중첩을 줄일수 있어 코드의 가독성을 높일수 있다.    
 예상하는 결과 파악이 용이하다. (예상 결과가 함수 끝에 리턴됨)   
 조건이 충족되지 않는 경우 나머지 부분이 실행문을 종료 시킨다.    
 함수는 에러가 발생하는 즉시 종료 되기 떄문에 의도하지 않은 코드의 실행을 막아준다.    
   
 아래의 코드는 if 조건문이 중첩되어 가독성이 떨어진다.    
 코드의 내용을 파악하기도 어렵고 조건문에 대응하는 else를 확인하기도 어렵다.    
 또한 예상되는 결과를 찾는 과정도 if문을 읽어가며 확인해야 한다.   


```javascript

public String returnStuff(SomeObject argument1, SomeObject argument2) {
    if (argument1.isValid()) {
        if (argument2.isValid()) {
            SomeObject otherVal1 = doSomeStuff(argument1, argument2)

            if (otherVal1.isValid()) {
                SomeObject otherVal2 = doAnotherStuff(otherVal1)

                if (otherVal2.isValid()) {
                    return "Stuff";
                } else {
                    throw new Exception();
                }
            } else {
                throw new Exception();
            }
        } else {
            throw new Exception();
        }
    } else {
        throw new Exception();
    }
}


```

 위의 코드는 *안티패턴*이 포함되어있다.   

####  Else Considered Smelly   
 : 조건이 복잡할 수록 else문은 더 복잡해진다. 코드를 읽는 사람은 이 코드를 다시 거꾸로 읽어봐야 하기 때문이다.       
####  ArrowAntiPattern   
```javascript
  if    
   if    
     if    
       if    
         do something    
       endif    
     endif    
   endif    
 endif    

```

### Early return pattern으로 수정해보자! 
```
public String returnStuff(SomeObject argument1, SomeObject argument2){
      if (!argument1.isValid()) {
            throw new Exception();
      }

      if (!argument2.isValid()) {
            throw new Exception();
      }

      SomeObject otherVal1 = doSomeStuff(argument1, argument2);

      if (!otherVal1.isValid()) {
            throw new Exception();
      }

      SomeObject otherVal2 = doAnotherStuff(otherVal1);

      if (!otherVal2.isValid()) {
            throw new Exception();
      }

      return "Stuff";
}


```

### TIL
자바스크립트를 항상 공부해서 대부분의 모르는 내용이 없다고 생각했는데    
오늘 정말 깔끔하게 코딩할 수 있는 Early return pattern을 알게 되서 뿌듯하다.   
   
나는 자바스크립트 기본기부터 다지려고 강의를 듣게 되었다.   
인프런에서 웹 프론트엔드를 위한 자바스크립트 첫 걸음을 듣고있는데 
자바스크립트 기본기가 부족한 사람들은 꼭 강의를 들어보면 도움이 될것 같다.  
자바스크립트 알지만 오늘 내가 포스팅 한 내용을 모르면 들어야 한다고 본다.    





