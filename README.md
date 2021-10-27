# Java

자바 웹 개발 프레임워크인 Spring을 배우기 전에, 자바 언어와 객체 지향 개념의 기본을 탄탄히 다지기 위해 공부했습니다.

아래 내용은 **Do it! 자바 프로그래밍 입문** 도서를 참고하며, 이해한 내용을 바탕으로 기록했습니다.

더욱 자세한 설명을 원하시면 위 책을 직접 읽어보시는 것을 추천드립니다.

---

- 자바는 1991년 제임스 고슬링을 비롯한 선 마이크로시스템스 연구원들이 처음 개발했다.
- 가전제품이나 휴대용 장치 등에 사용하는 소프트웨어를 만들기 위해 **독립적으로 작동하는 더 안정된 프로그래밍 언어**가 필요하여 자바가 만들어졌다.

아래는 자바의 특징을 나열한 것이다.

### 플랫폼에 종속 X

참고) 플랫폼(Platform)이란 프로그램이 실행되는 환경을 뜻한다.

- 자바에서는 .exe의 실행 파일 대신 .class의 확장자를 가진 바이트 코드를 생성
- 생성된 바이트 코드를 **자바 가상 머신**에서 실행하여, 각 운영체제에 맞는 실행 파일 생성
- 이러한 특성은 초반에 프로그램의 실행 속도를 저하시킨 원인이 되었지만, 자바 컴파일러가 JIT 컴파일 방식으로 개선되며 실행 속도가 개선됨

참고) JIT(Just In Time) 컴파일러는 실행 시점에 기계어 코드 생성, 같은 코드 반복일 경우 이전에 만든 기계어 재사용의 특징이 있다.

### 객체 지향 언어

- 객체 지향 프로그래밍이란 일의 순서가 아닌 **여러 객체의 협력(상호 관계)을 통해 프로그램을 구현하는 것**
- 공통으로 사용하는 부분을 수정하지 않고도 새 기능 쉽게 추가 가능
- **유지보수**가 쉽고 **확장성**이 좋은 프로그램이 될 수 있음

### 안정적인 프로그램

- 자바는 포인터 문법을 제공하지 않아 메모리를 직접 제어하지 않음. 그에 따라 오류 위험성을 줄임
- Garbage Collector를 이용해 동적 메모리를 수거하므로 효율적인 메모리 관리가 가능함

### 오픈 소스

- JDK(Java Development Kit)를 가지고 있어 프로그램을 빠르게 개발할 수 있음
- 자바를 활용한 오픈 소스가 많이 개발되어 있기 때문에 그 소스들을 연동하여 더 풍부한 기능을 빠르게 구현할 수 있음 

참고) JDK는 클래스, 자료 구조, 네트워크, 입출력, 예외 처리 등에 최적화된 알고리즘 라이브러리를 제공

---

## 자바 기초

### 변수명 정하기

- 변수명은 사용 목적에 맞게 의미를 부여하여 만들어야 한다.
- 영문자(대소문자)와 숫자를 사용할 수 있고, 특수문자는 $, _ 등만 사용할 수 있다.
- 숫자로 시작할 수 없다.
- 자바에서 이미 사용 중인 예약어는 사용할 수 없다.
- **Camel Notation**이란 중간에 다른 뜻의 단어가 등장하면 첫 글자를 대문자로 사용하는 것이다. (numberOfStudent, isGood)

### 자바 자료형

- 자바에서 제공하는 자료형에는 기본 자료형과 참조 자료형이 있음
- 참조 자료형은 클래스형임

아래는 기본 자료형이다.
- 정수형 : byte(1byte), short(2byte), **int(4byte)**, long(8byte)
- 실수형 : float(4byte), double(8byte)
- 문자형 : char(2byte)
- 논리형 : boolean(1byte)

아래는 자료형의 특징이다.
- long 형은 숫자 뒤에 ```L```, ```l```의 식별자를 붙여야 한다. 또한 float형은 ```F```, ```f```를 붙여야 함
- 컴퓨터 내부에서 문자를 표현할 때 특정 정수 값으로 정한다. 코드 값을 모아둔 것을 '문자 세트', 문자를 코드 값으로 변환하는 것을 '문자 인코딩', 그 반대를 '문자 디코딩'이라고 함
- 자바는 유니코드(unicode)에 기반하여 문자를 표현하기 때문에, char형은 2byte를 사용

### 상수

- 상수(constant)는 항상 변하지 않는 값임
- 값 초기화 후에 다시 값 변경 불가
- 상수를 선언할 때 자료형 앞에 ```final```을 붙임
- 이름은 주로 대문자를 사용하고, _ 기호를 사용해 여러 단어를 연결함

### 리터럴

- 프로그램에서 사용하는 모든 숫자, 문자, 논리값을 일컫는 말
- 프로그램이 시작할 때 시스템에 같이 로딩되어 constant pool에 놓임
- 이 리터럴은 변수나 상수 값으로 대입할 수 있음

(일반 연산자에 대한 기록은 생략하겠습니다.)

### 비트 연산자

비트 논리 연산자
- ```&``` : 두 개의 비트 값이 모두 1인 경우에만 1이 됨
- ```|``` : 하나의 비트만 1이어도 1이 됨
- ```^``` : 같은 값이면 0, 다른 값이면 1
- ```~``` : 비트 값이 0이면 1, 1이면 0으로 바꿈

비트 이동 연산자
- ```<<``` : 왼쪽으로 비트 이동. 왼쪽으로 n비트 이동하면 기존 값에 2의 n제곱만큼 곱함
- ```>>``` : 오른쪽으로 비트 이동. 오른쪽으로 n비트 이동하면 기존 값을 2의 n제곱만큼 나눔
- ```>>>``` : 오른쪽으로 비트 이동, 왼쪽에 채워지는 비트 값이 부호 비트와 상관없이 무조건 0이 됨

(제어문과 반복문에 대한 기록은 생략하겠습니다.)

---

## 객체 지향 프로그래밍

- 객체 지향 프로그래밍(Object-Oriented Programming; OOP)은 객체를 기반으로 프로그래밍 하는 것
- 한 마디로, 객체를 만들고 **객체 사이에 일어나는 일을 구현**하는 것
- 우리는 객체를 먼저 정의하고 각 객체가 어떤 기능을 제공할지, 객체 간 협력을 어떻게 구현할 것인지 고민해야 함

### 클래스

- 클래스는 **객체의 속성과 기능**을 코드로 구현한 것
- 클래스는 속성(멤버 변수)과 메서드를 가짐
- 클래스 이름은 대문자로 시작함 (coding convention)

아래는 클래스를 정의하는 문법이다.
```
(접근 제어자) class 클래스 이름 {
  멤버 변수;
  메서드;
}
```

### 멤버 변수 (member variable)

- **객체가 가지는 속성**을 클래스 내부에 변수로 선언한 것
- 멤버 변수(member variable)는 다른 말로 속성(property) 또는 특성(attribute) 등으로 표현함
- 멤버 변수의 자료형은 기본 자료형(int, double ..), 참조 자료형(String, Date, 직접 만든 클래스 ..) 둘 다 가능하다.

참고) 패키지는 클래스 파일의 묶음이다. 패키지는 계층 구조를 가지고, 이 계층 구조를 잘 구성해야 유지 보수가 편리하다.

### 메서드 (method)

- 메서드는 함수에 객체 지향 개념이 포함된 용어
- 멤버 변수를 사용하여 **클래스의 기능**을 구현한 것

아래는 클래스와 내부의 멤버 변수, 메서드를 구현한 코드이다.
```java
public class Student {
    int studentID;
    String studentName;
    int grade;
    String address;

    public String getStudentName() {
        return studentName;
    }

    public void setStudentName(String name) {
        studentName = name;
    }
}
```

### main() 함수

- 클래스를 사용하려면 main() 함수가 있어야 함. 이 main() 함수는 클래스 내부에 만들지만, 클래스의 메서드는 아님
- 자바 가상 머신(JVM)은 프로그램을 시작할 때 main() 함수를 가장 먼저 호출함
- main() 함수는 클래스 내부에 만들어도 되고, 외부에 테스트용 클래스를 만들어 사용해도 됨
- 테스트 클래스와 실제 클래스 파일이 각각 다른 패키지에 있을 경우 import문을 사용해 클래스를 불러와야 함.

### 인스턴스 (instance)
 
- main() 함수에서 클래스를 사용할 때 new 예약어와 생성자를 사용해 클래스를 생성
- 클래스가 생성된다는 것은 클래스를 실제 사용할 수 있도록 힙 메모리를 할당 받는 것임
- 생성된 클래스를 **인스턴스**라고 하고, 인스턴스를 가리키는 클래스형 변수를 **참조 변수**라고 함
- 즉, 인스턴스는 클래스가 메모리 공간에 생성된 상태 (객체라고도 함)

아래는 new 예약어를 사용하는 방법이다.
```
클래스형 변수명 = new 생성자;
```











