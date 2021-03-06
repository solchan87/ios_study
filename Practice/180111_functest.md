# Swift 기초 문법
> 2018.01.11 업데이트

## 변수와 상수 그리고 함수
* 변수 : 프로그램에서 데이터의 저장 공간을 담당하며, 변하는 값을 말한다.`var`
> 키워드 + 변수명(Name): + 변수 타입(Type) = 값(Value) / 문법 예)
```swift
var vName: Any = 3
```
* 상수 : 프로그램에서 데이터의 저장 공간을 담당하며, 변하지 않는 값을 말한다.`let`
> 키워드 + 변수명(Name): + 변수 타입(Type) = 값(Value) / 문법 예)
```swift
let lName: Any = 3
```
* 함수 : 프로그램이 실행되는 행동을 담당
> 키워드 + 함수명(Name) + 입력값(Input Value) + 함수 내용(Action) + 결과 타입
```swift
func fName(Parameter: Any) -> Any
{
    //함수 내용
}
```


#### 1-1)연습
나만의 person Class를 만들어 보시오.
```swift
import Foundation

class Person {
    var name: String = ""
    var age: Int = 0
    var eye: Double = 0
    var tall: Double = 0
    
    func eat(money: Int) {
        print("\(name)이(가) \(money)원의 점심을 먹습니다.")
    }
    
    func run(distance: Int, speed: Int) {
        print("\(name)이(가) \(speed)km/h의 속도로 \(distance)m를 달렸습니다.")
    }
    
    func checkBody() {
        print("\(name)의 나이는 \(age)살이고 키는 \(tall)cm, 시력은 \(eye)입니다.")
    }
    
}
```
>연산자 앞,뒤의 space(공백)은 동일하게 해줘야 오류가 안난다.

### 주석 처리
* 주석 앞에 `//`를 사용해서 한줄씩 주석처리를 할 수 있다.
> `command` + `/` 단축키로 주석을 설정/해제할 수 있다.
```swift
//주석을 작성할 수 있다.
//라인별로 주석을 작성해야 된다.
```
* `/*` 시작 기호와 `*/` 끝기호를 사용하여 여러 라인의 줄을 모두 주석 처리할 수 있다.
```swift
/*
    이안의
    모든 내용은
    주석으로 처리가
    가능하다.
*/
```
* function 윗줄에 커서를 놓고 `option`+`command`+`/` 를 누르면 해당 펑션의 quick help 문서를 만들어 Description을 수정할 수 있다.
```swift
/// <#Description#>
    func test() {
        
    }
```

### Class
클래스는 프로그램 코드 블럭을 만들도록 유연하게 구성하는 것이 일반적인 목적이며, 속성과 메소드는 클래스에 상수, 변수, 함수로서 동일한 구문을 정확하게 사용하여 기능을 추가하도록 정의한다.
* 일반적으로 클래스 안에서는 변수의 선언과 함수의 선언만 이뤄진다. 클래스 안에서 연산을 할 수가 없다.  
* 클래서에서는 시작 시 함수명의 위치만 확인하기 때문에 함수간 위치는 실행에 전혀 지장이 없다.  
* 일반적으로 클래스 앞에는 `internal`이 숨겨져 있다.  

###객체(Instance)
* 클래스안에 정의한 함수를 객체화 하여 사용할 수 있도록 한다.
> 함수 내에 `className()`을 선언하여 인스턴스(객체 만들기)를 생성한다.
* 인스턴스에 변수를 저장한다.
```swift
var iName: className = className()
```
* 인스턴스의 속성(변수), 함수 접근 및 실행한다.(닷. 문법 사용)
```swift
iName.vName = "name"
iName.start()
```

#### 1-2)연습
1-1에서 만든 코드의 객체를 생성하여 코드를 확인해보시오.
```swift
// 시작지점!
        let solchan: Person = Person()
        solchan.name = "안솔찬"
        solchan.age = 32
        solchan.eye = 1.2
        solchan.tall = 165.6
        
        solchan.eat(money: 5000)
        solchan.checkBody()
        solchan.run(distance: 100, speed: 20)
        
        let minsoo: Person = Person()
        minsoo.name = "김민수"
        minsoo.eat(money: 6000)
        
        let eunmi: Person = Person()
        eunmi.name = "김은미"
        eunmi.run(distance: 1000, speed: 12)
```
결과
```
안솔찬이(가) 5000원의 점심을 먹습니다.
안솔찬의 나이는 32살이고 키는 165.6cm, 시력은 1.2입니다.
안솔찬이(가) 20km/h의 속도로 100m를 달렸습니다.
김민수이(가) 6000원의 점심을 먹습니다.
김은미이(가) 12km/h의 속도로 1000m를 달렸습니다.
```