# Java

## 객체지향언어
### 1.1 특징
- 재사용성, 유지보수, 중복된 코드의 제거, 
    1. 코드의 재사용성이 높다. 
    2. 코드의 관리가 용이하다. 
    3. 신뢰성이 높은 프로그램이 가능하다.
+ 제어자와 메서드를 이용해 데이터를 보호하고, 올바는 값을 유지하도록 하며, 코드의 중복을 제거하여 코드의 불일치로 인한 오동작을 방지할 수 있다.


## 2.클래스와 객체

### 2.1 정의와 용도
- 클래스를 통해 객체를 만들면 매번 설계하지 않고 객체를 생성해서 사용할 수 있음.
    - 클래스 : 객체를 정의해놓은 것, 객체를 생성하는 데 사용.
    - 객체 : 실존하는 것, 가지고 있는 속성과 기능에 따라 용도가 정해짐.

### 2.2 객체와 인스턴스

- 인스턴스(instance) : 클래스로부터 만들어진 객체
- 인스턴스화(instantiate) : 클래스로부터 객체를 만드는 과정

### 2.3 객체의 구성요소 
- 속성(property) : 멤버변수(member variable), 특성(attribute), 필드(filed), 상태(state)
- 기능(funcfion) : 메서드(Method), 함수(function), 행위(behavior)

### 2.4 인스턴스의 생성과 사용
- 클래스 명 변수명;
- 변수명 = new 클래스명();
```
Tv t ; //참조변수 t선언
t = new Tv();  //new 연산자로 인스턴스 생성. 초기화.
```
- 인스턴스는 참조변수를 통해서만 다룰 수 있으며, 참조변수의 타입은 인스턴스의 타입과 일치해야 한다.

### 2.5 객체 배열
- 객체를 배열로 다루는 것으로 객체의 주소가 저장됨.
- 참조변수들을 하나로 묶은 참조변수 배열.
- 같은 타입의 객체만 저장가능. 

```
Tv[] arr = new Tv[3]; // 참조변수 객체배열 생성
arr[0] = new Tv();
arr[1] = new Tv();
arr[2] = new Tv(); 
// 객체를 생성해서 배열의 각 요소에 저장 

for(int i=0; i<arr.length; i++){
    arr[i] = new Tv();
}
```
### 2.6 프로그래밍 관점에서 클래스

1. 클래스-데이터와 함수의 결합
- 프로그래밍 언어에서 데이터 처리를 위한 데이터 저장 형태 발전과정 : 변수->배열->구조체->클래스
    + 변수 : 하나의 데이터를 저장할 수 있는 공간
    + 배열 : 같은 종류의 여러 데이터를 하나의 집합으로 저장할 수 있는 공간
    + 구조체 : 서로 관련된 여러 데이터를 종류에 관계없이 하나의 집합으로 저장할 수 있는 공간
    + 클래스 : 데이터와 함수의 결합(구조체 +함수)
- 객체지향언어에서는 변수(데이터)와 함수를 하나의 클래스에 정의하여 관계가 깊은 변수와 함수들을 함께 다룰 수 있다.

2. 클래스-사용자정의 타입(User-defined type)
    - 개발자가 서로 관련된 변수들을 묶어서 하나의 타입으로 추가하는 것


## 3.변수와 메서드 

### 3.1 선언 위치에 따른 변수의 종류
- 변수 : 클래스변수, 인스턴스변수, 지역변수
    1. 인스턴스변수(instance variable) : 클래스 영역에 선언, 인스턴스 생성 시 생성, 독립적이 저장공간으로 각자 다른 값을 가질 수 있음. 
    2. 클래스변수(class variable) : static+인스턴스 변수, 공동된 저장공간 공유.  
    3. 지역변수(local variable) : 메서드 내에서 사용 가능. 블럭을 벗어나면 사용할 수 없음.

### 3.2 메서드
- 특정 작업을 수행하는 일련의 문장드을 하나로 묶은 것. 반드시 결과를 반환한다. 
- 메서드를 사용하는 이유는 높은 재사용성, 중복된 코드의 제거, 프로그램의 구조화가 있다.

### 3.3 메서드의 선언과 구현
- 메서드는 선언부와 구현부로 구분된다.
```
int add(int a, int b){ //선언부
    int result = a+b;  //구현부
    return result;
}
```
- 반환타입이 없는 경우 void
- 매개변수는 여러 개 선언 가능, return은 단 하나의 값만 반환 가능.

### 3.4 메서드의 호출

- 인자와 매개변수 
    - 인자(argument) : 메서드를 호출할 떄 지정해준 값들. 인자의 개수와 순서는 호출된 메서드에 선언된 매개변수와 일치해야한다. 타입이 일치하거나 형 변환도 가능해야한다.

### 3.5 return문

현재 실행한 메서드를 종료하고 호출한 메서드로 되돌아간다. 
모든 메서드는 적어도 하나의 return문이 필요하며, void인 경우, 컴파일러가 자동으로 return;를 자동적으로 추가한다.

### 3.6 기본형 매개변수와 참조형 매개변수 
매개변수 타입이 기본형(primitive type)이면 기본형의 값이, 참조형(reference)이면 인스턴스의 주소가 복사된다.
기본형으로 선언하면 저장된 값만 얻어오지만, 참조형으로 선언하면 값이 저장된 곳의 주소를 알 수 있기 때문에 값을 읽어오는 것은 물론 값을 변경하는 것도 가능하다.

### 3.7 참조형 반환타입
반환타입이 참조형이라는 것은 메서드가 '객체의 주소'를 반환하는 것을 의미한다.

### 3.8 재귀호출
- 메서드 내부에서 메서드 자신을 다시 호출하는 것을 말한다. 반복문보다 재귀호출의 수행시간이 더 오래걸리지만 사용하면 단순한 구조로 바뀔 수 있다. 
- 재귀호출의 대표적인 사례로는 '팩토리얼(factorial)'이 있다. 
    - 한 숫자가 1이 될때까지 1씩 감소시켜가면서 계속해서 곱하는 것.
```
static int factorial(int n) {
    int result=0;
    if(n==1) {
        result=1;
    }else {
        result=n*factorial(n-1); // 재귀호출
    }
        return result;
}
```

### 3.9 클래스 메서드(static메서드)와 인스턴스 메서드
- 클래스 메서드 : 인스턴스와 관계없는 메서드. 객체를 생성하지 않고도 '클래스이름.메서드이름(매개변수)'로 호출가능. 
- 인스턴스 메서드 : 인스턴스 변수와 관련된 작업을 수행하는 메서드. 반드시 객체를 생성해야만 호출 할 수 있음.

    1. 클래스 설계 시, 멤버변수 중 모든 인스턴스에 공통으로 사용하는 것에  static을 붙인다. 
        - 모든 인스턴스에 값이 유지되어야 하는 변수는 static를 붙여서 클래스로 변수로 정의.
    2. 클래스변수는 인스턴스 생성여부와 관계없이 사용가능하다.
        - 클래스가 메모리에 올라갈 때 자동으로 생성된다.
    3. 클래스메서드는 인스턴스 변수를 사용할 수 없다.
        - 인스턴스 멤버가 존재하는 시점에는 클래스 멤버는 항상 존재하지만, 클래스 멤버가 존재하는 시점에 인스턴스 멤버가 존재하지 않을 수 있다.
        - 인스턴스 멤버간 호출은 얼마든지 사용가능하다.
    4. 메서드 내에서 인스턴스 변수를 사용하지 않는다면 static을 붙이는 것을 고려한다.
        - 메서드의 작업요소 중에서 인스턴스 병수를 필요호 하지 않는 경우 static을 붙일 수 있다. 
        - 메서드 호출시간이 짧아져 성능이 향상된다.

### 3.10 클래스멤버와 인스턴스 멤버간의 참조와 호출


## 4.오버로딩(overloading)
### 4.1 오버로딩이란?
- 한 클래스 내에 같은 이름의 메서드를 여러 개 정의 하는 것

### 4.2 오버로딩의 조건
1. 메서드 이름이 같아야한다.
2. 매개변수의 개수 또는 타입이 달라야한다.
    - 대표적인 오버로딩의 예 : println 메서드

### 4.3 오버로딩의 장점
1. 여러 메서드를 하나의 이름으로 정의해 같은 기능을 하는 메서드를 구분할 수 있음.
2. 메서드의 이름를 절약할 수 있다. 

### 4.4 가변인자(variable argument)와 오버로딩
- 가변인자
JDk1.5부터 동적으로 지정하는 가변인자 사용 가능. 
'타입...변수명' 으로 선언.
가변인자는 내부적으로 배열을 이용하느 것으로 호출할 때마다 배열이 새롭게 생성.
가능한 가변인자를 사용한 메서드는 오버로딩하지 않는 것이 좋다.

## 5. 생성자(Constructor)
### 5.1 생성자란?
- 인스턴스가 생성될 때 호출되는 '인스턴스 초기화 메서드'다. 메서드와 유사하지만 리터값이 없다.
- 생성자의 생성 조건은 1. 클래스와 이름이 같아야하고 2. 리턴값이 없다 는 것이다.

### 5.2 기본 생성자(default Constructor)
- 모든 클래스에는 반드시 하나의 생성자가 필요하다. 별도의 생성자가 없을 경우 컴파일러가 기본으로 기본생성자를 제공한다.

### 5.3 매개변수가 있는 생성자
- 다양한 생성자를 제공하면 인스턴스 생성 후에 별도로 초기화를 하지 않아도 된다.
```
Car c = new Car("white", "auto", 4);
```
### 5.4 생성자에서 다른 생성자 호출하기 - this(), this
- this를 사용하면 생성자 간에 호출이 가능하다. 단, 반드시 첫 줄에서만 호출이 가능하다.
    - 'this'는 참조변수로 인스턴스 자신을 가리킨다.

### 5.5 생성자를 이용한 인스턴스의 복사 

- 현재 사용하고 있는 인스턴스와 같은 상태를 갖는 인스턴스를 하나 더 만들고자 할 때 생성자를 이용할 수 있다. 
- 생성자를 사용하면 간결하고 직관적인 객체지향적 코드 작성이 가능하다.
    - 인스턴스 생성 시 결정해야하는 2가지 상황
        - 클래스 : 어떤 클래스의 인스턴스를 생성할 것인가?
        - 생성자 : 선택한 클래스의 어떤 생성자로 인스턴스를 생성할 것인가?


## 6.변수의 초기화
### 6.1 변수의 초기화 
- 변수를 선언하고 처음으로 값을 지정하는 것
- 멤버변수(클래스변수, 인스턴스변수)와 배열의 초기화는 선택적이지만, 지역변수의 초기화는 필수적이다.
- 각 타입별 초기값(default value)
    - boolean : false
    - char : '\n0000'
    - byte, short, int : 0
    - long : 0L
    - float : 0.0f
    - double : 0.0
    - 참조형 변수 : null

- 멤버변수의 초기화 방법
    - 명시적 초기화(explicit initialzation) : 변수를 선언과 동시에 초기화 하는 것. 
    - 생성자 (constructor)
    - 초기화 블럭(initialization block)
        - 클래스 초기화 블럭 : 클래스변수의 복잡한 초기화에 사용된다. 메모리에 처음 로딩될 때 한 번만 수행.
        - 인스턴스 초기화 블럭 : 인스턴스변수의 복잡한 초기화에 사용된다. 인스턴스를 생성할 때마다 수행.     
        ```
        class InitBlock{
            static{
                /* 클래스초기화 블럭 */
            }
            {/* 인스턴스초기화 블럭 */}
        }
        ```
    - 생성자보다 인스턴스 초기화 블럭이 먼저 수행됨!

### 6.2 멤버변수의 초기화 시기와 순서
- 클래스변수의 초기화 시점 : 클래스가 처음 로딩될 때 단 한번 초기화 된다.
- 인스턴스 변수의 초기화 시점 : 인스턴스가 생성될 때마다 각 인스턴스별로 초기화가 이루어진다.

- 클래스변수의 초기화 순서 : 기본값 -> 명시적 초기화 -> 클래스 초기화 블럭
- 인스턴스 변수의 초기화 순서 : 기본값 -> 명시적 초기화 -> 인스턴스 초기화 블럭 -> 생성자


# 객체지향 프로그래밍
## 1. 상속
### 1.1 상속의 정의와 장점
- 정의 : 기존의 클래스를 재사용하여 새로운 클래스를 작성하는 것
- 장점 : 공통적으로 코드를 관리할 수 있어 코드의 추가 및 변경이 용이 
- 방법 : 클래스 이름 + extends
- 상속관계
    - 조상클래스 : 부모(parent)클래스, 상위(super)클래스, 기반(base)클래스
    - 자손클래스 : 자식(child)클래스, 하위(sub)클래스, 파생된(derived) 클래스
- 조상클래스가 변경되면 자손클래스는 자동으로 영향을 받음. 자손 클래스의 변경은 조상클래스에 아무런 영향을 주지 않음. 
- 특징
    1. 멤버만 상속, 생성자와 초기화 블럭은 상속X  
    2. 자손클래스의 멤버 개수는 조상클래스보다 항상 같거나 많다.
     전체 프로그램을 구성하는 클래스들을 면밀하게 분석하여, 클래스 간의 상속관계를 적절히 맺어주는 것이 객체지향 프로그래밍에서 가장 중요한 부분임 

### 1.2 클래스 간의 관계 - 포함관계
클래스의 멤버변수로 다른 클래스의 참조변수를 선언하는 것.
```
class Point{
    int x; int y;
}
class Cricle{
    Point c = new Point(); //클래스의 포함관계 
    int r;
}
```

### 1.3 클래스 간의 관계 설정하기
- 클래스 작성 시 상속관계를 맺을 것인지 포함관계를 맺을 것인지 결정하는 것은 혼란스러울 수 있다.
    - 상속관계 : is -a (-은 -이다.)
    - 포함관계 : has -a (-은 -를 가지고 있다.)

### 1.4 단일 상속
자바에서는 오직 단일 상속만 허용함.
둘 이상의 클래스로부터 상속 받을 수 없음.

### 1.5 Object클래스 - 모든 클래스의 조상
- 모든 클래스 상속계층도 최상위에 있는 조상클래스 
- toString()이나 equals()와 같은 메서드를 따로 정의하지 않고도 사용할 수 있는 이유는 메서드들이 Object클래스에 정의된 것들이기 때문이다.


## 2. 오버라이딩(overridding)

### 2.1 오버라이딩이란?
- 정의 : 조상클래스로부터 상속받은 메서드의 내용을 변경하는 것
- 조건 
    - 자손클래스에서 오버라이딩하는 메서드는 이름, 매개변수, 반환타이이 같아야한다.
    - 조상클래스의 메서드를 자손클래스에서 오버라이딩할 때,
        - 접근 제어자를 조상 클래스를 메서드보다 좁은 범위로 변경할 수 없다.
        - 예외는 조상 클래스의 메서드보다 많이 선언할 수 있다.
        - 인스턴스 메서드를 static메서드로 또는 그 반대로 변경할 수 없다.

### 2.2 오버로딩 vs 오버라이딩
- 오버로딩 : 기족에 없는 새로운 메서드를 정의하는 것(new)
- 오버라이딩 : 상속받은 메서드의 내용을 변경하는 것(change, modify)

### 2.3 super
- 자손클래스에서 조상클래스로부터 상속받은 멤버를 참조하는에 사용되는 참조변수 
- 상속받은 멤버와 자신의 멤버 이름이 같을 때 super를 붙여서 구별함.
- 조상클래스의 메서드를 자손 클래스에서 오버라이딩한 경우에 super를 사용.
- super역시 this과 마찬가지로 static메서드에서 사용할 수 없고 인스턴스메서드에서 사용할 수 있다.

### 2.4 super() - 조상클래스의 생성자
- 조상클래스의 생성자를 호출할 때 사용

## 3. 패키지(package)
- 정의 : 클래스의 묶음 
- 특징 
    - 하나의 소스파일에는 첫 번째 문장으로 단 한 번의 패키지 선언만 허용한다.
    - 모든 클래스는 반드시 하나의 패키지에 속해야한다.
    - 패키지는 .을 구분자로 계층구조를 구성할 수 있다.
    - 패키지는 물리적으로 클래스파일(.class)을 포함하는 하나의 디렉토리이다.

- 패키지의 선언
    - 클래스명과 구분하기 위해 소문자로 하는 것을 원칙으로 함.
```
package 패키지명;
```

#### import문
- 컴파일러에게 소스파일에 사용된 클래스의 패키지에 대한 정보를 제공하는 것.
- 사용하고자 하는 클래스의 패키지를 미리 명시해주면 소스코드에 사용되는 클래스이름에서 패키지명은 생략할 수 있음.

## 4.제어자(modifier)
### 4.1 제어자란? 
- 클래스, 변수 또는 메서드의 선언부에 함께 사용되어 부가적인 의미를 부여함.
- 클래스, 멤버변수, 메서드에 주로 사용되며, 하나의 대상에 대해서 여러 제어자를 조합해서 사용할 수 있음.

#### 4.1.1 static - 클래스의, 공통적인
    - static이 사용될 수 있는 곳 : 멤버변수, 메서드, 초기화 블럭
    - static이 붙은 멤버변수와 메서드, 그리고 초기화 블럭은 인스턴스가 아닌 클래스에 관계된 것이기 때문에 인스턴스를 생성하지 않고도 사용할 수 있음.

#### 4.1.2 final - 마지막의, 변경될 수 없는
    - final이 사용될 수 있는 곳 : 클래스, 메서드, 멤버변수, 지역변수
    - 인스턴스 변수의 경우 생성자에서 초기화할 수 있다. 

#### 4.1.3 abstract - 미완성의, 추상의 
    - 메서드의 선언부만 작성하고 실제 수행내용은 구현하지 않는 추상메서드 선언
    - abstract가 사용될 수 있는 곳 : 클래스, 메서드
    - 추상클래스는 아직 완성되지 않은 메서드가 존재하는 '미완성 설계도' 로 인스턴스를 생성할 수 없다.
    
### 4.2 접근 제어자(access modifier)
- 멤버 또는 클래스에 사용되어 해당하는 멤버 또는 클래스를 외부에서 접근하지 못하도록 제한하는 역할
- 접근제어자가 사용될 수 있는 곳 - 클래스, 멤버변수, 메서드, 생성자
    - private : 같은 클래스 내에서만 접근 가능
    - default : 같은 패키지 내에서만 접근 가능
    - protected : 같은 패키지 내, 다른 패키지의 자손클래스에서 접근 가능
    - public : 접근 제한이 없음.

#### 4.2.1 접근 제어자를 이용한 캡슐화(encapsulation)
- 클래스의 내부에 선언된 데이터를 보호하기 위해 사용
- 데이터가 유효한 값을 유지하고, 비밀번호나 같은 데이터를 외부에서 함부로 변경하지 못하도록 하기 위해서 외부로부터의 접근을 제한하는 것.
    - get : 멤버변수의 값을 반환하는 일
    - set : 매개변수에 지정된 값을 검사하여 조건에 맞는 값일 때만 멤버변수의 값을 변경하도록 작성.
        - 상속을 통해 확장될 것이 예상되는 클래스의 경우 : protected사용 (private은 자손 클래스에서도 접근이 불가능 해 사용할 수 X)

- 생성자의 접근제어자 
    - 생성자의 접근제어자는 클래스의 접근제어자와 같지만, 다르게 설정할 수 있다.
    - 생성자가 private인 클래스는 다른 클래스의 조상이 될 수 없다. 자손클래스에서 호출이 불가능하기 때문.

### 4.3 제어자의 조합
- 사용가능한 제어자
    - class : public, default, final, abstract
    - method : 모든 접근 제어자, final, abstract, static
    - 멤버변수 : 모든 접근 제어자, final, static
    - 지역변수 : final

- 제어자 조합 사용 시 주의해야 할 사항
    1. 메서드에 static과 abstract는 함께 사용할 수 없다.
    2. 클래스에 abstract와 final은 함께 사용할 수 없다.
    3. abstract메서드의 접근 제어자가 private일 수 없다.
    4. 메서드에 private와 final을 같이 사용할 필요는 없다. 

## 5. 다형성(polymorphism)
### 5.1 다형성이란?
