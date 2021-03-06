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
- long 형은 숫자 뒤에 `L`, `l`의 식별자를 붙여야 한다. 또한 float형은 `F`, `f`를 붙여야 함
- 컴퓨터 내부에서 문자를 표현할 때 특정 정수 값으로 정한다. 코드 값을 모아둔 것을 '문자 세트', 문자를 코드 값으로 변환하는 것을 '문자 인코딩', 그 반대를 '문자 디코딩'이라고 함
- 자바는 유니코드(unicode)에 기반하여 문자를 표현하기 때문에, char형은 2byte를 사용

### 상수

- 상수(constant)는 항상 변하지 않는 값임
- 값 초기화 후에 다시 값 변경 불가
- 상수를 선언할 때 자료형 앞에 `final`을 붙임
- 이름은 주로 대문자를 사용하고, _ 기호를 사용해 여러 단어를 연결함 (PI)
- `final` 키워드를 붙인 메서드는 **오버라이딩 불가능**
- `final` 키워드를 붙인 클래스는 **상속 불가능**
- `static`과 `final`은 다른 것. (`static`은 특정 클래스의 인스턴스 모두가 공동으로 사용하는 클래스 변수/메서드)

### 리터럴

- 프로그램에서 사용하는 모든 숫자, 문자, 논리값을 일컫는 말
- 프로그램이 시작할 때 시스템에 같이 로딩되어 `constant pool`에 놓임
- 이 리터럴은 변수나 상수 값으로 대입할 수 있음

*(일반 연산자에 대한 기록은 생략하겠습니다.)*

### 비트 연산자

비트 논리 연산자
- `&` : 두 개의 비트 값이 모두 1인 경우에만 1이 됨
- `|` : 하나의 비트만 1이어도 1이 됨
- `^` : 같은 값이면 0, 다른 값이면 1
- `~` : 비트 값이 0이면 1, 1이면 0으로 바꿈

비트 이동 연산자
- `<<` : 왼쪽으로 비트 이동. 왼쪽으로 n비트 이동하면 기존 값에 2의 n제곱만큼 곱함
- `>>` : 오른쪽으로 비트 이동. 오른쪽으로 n비트 이동하면 기존 값을 2의 n제곱만큼 나눔
- `>>>` : 오른쪽으로 비트 이동, 왼쪽에 채워지는 비트 값이 부호 비트와 상관없이 무조건 0이 됨

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
- 객체의 기능을 구현하기 위해 클래스 내부에 구현되는 함수
- 멤버 함수(member function)라고도 함
- 메서드의 이름은 그 객체를 사용하는 객체(클라이언트)에 맞게 짓는 것이 좋음

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
- 생성된 클래스를 **인스턴스**(혹은 객체)라고 하고, 인스턴스를 가리키는 클래스형 변수를 **참조 변수**라고 함
- 즉, 인스턴스는 클래스가 메모리 공간에 생성된 상태

아래는 new 예약어를 사용하는 방법이다.
```
클래스형 변수명 = new 생성자;
```

- 참조 변수에 도트 연산자(.)를 사용하여 멤버 변수와 메서드를 참조하여 사용 가능
- ```new Student()```와 같이 선언하면 이 인스턴스와 멤버 변수들은 힙 메모리(heap memory)에 저장

아래는 인스턴스를 생성하는 코드이다.
```java
Student studentAhn = new Student();
```
지역 변수 Ahn에 생성된 인스턴스를 대입한다는 것은, studentAhn에 인스턴스가 생성된 힙 메모리의 주소를 대입한다는 것과 같은 의미이다.

참고) 힙(heap)은 프로그램에서 사용하는 동적 메모리(dynamic memory)공간이다. 보통 객체가 생성될 때 사용하는 공간이다.

### 생성자 (basic.constructor)

- 생성자는 클래스를 처음 만들 때 멤버 변수나 상수를 초기화해줌
- 생성자가 없는 클래스는 자바 컴파일러에서 디폴트 생성자(default basic.constructor)를 자동으로 만듦
- 프로그래머가 디폴트 생성자를 직접 만드는 경우 필요에 따라 코드 구현 가능
- 인스턴스가 생성될 때 인스턴스 초기화를 위해 생성자를 직접 구현하기도 함

아래는 클래스 안의 디폴트 생성자를 코드로 구현한 것이다.
```java
public class Person {
  String name;
  float height;
  float weight;
  
  public Person() {}
}
```

### 생성자 오버로드 (basic.constructor overload)

- 생성자 오버로드는 클래스에 생성자가 두 개 이상 제공되는 것
- 필요에 따라 매개변수가 다른 생성자를 여러 개 만들 수 있음
- 경우에 따라 클래스에서 일부러 디폴트 생성자를 제공하지 않기도 함

참고) 객체 지향 프로그램에서 메서드 이름은 같고 매개변수만 다른 경우를 **오버로드**라고 한다.

아래는 생성자 오버로드를 구현한 코드이다.
```java
public class Person {
    String name;
    float height;
    float weight;

    public Person() {}

    public Person(String pname) {
        name = pname;
    }

    public Person(String pname, float pheight, float pweight) {
        name = pname;
        height = pheight;
        weight = pweight;
    }
}
```

### 정보 은닉 (information basic.hiding)

- 객체 지향 프로그램에서는 접근 제어자(access modifier)를 사용해 (클래스 내부 변수, 메서드, 생성자에 대한) **접근 권한**을 지정할 수 있음
- private으로 선언한 멤버 변수는 getter, setter 메서드(public으로 설정)로 접근 가능
- 정보 은닉은 클래스 내부에서 사용할 변수나 메서드를 private으로 선언하여 외부에서 직접 접근하지 못하도록 하는 것
- 정보 은닉은 객체 지향 프로그래밍의 특징

|접근 제어자|설명|
|-----|-----|
|public|외부 클래스 어디서나 접근 가능|
|protected|같은 패키지 내부와 상속 관계의 클래스에서만 접근 가능|
|아무것도 없는 경우|default이며 같은 패키지 내부에서만 접근 가능|
|private|같은 클래스 내부에서만 접근 가능|

### this 예약어

- this는 생성된 인스턴스 스스로를 가리키는 예약어
- this는 동적 메모리에 생성된 인스턴스의 위치를 직접 가리킴
- 또한 this는 생성자에서 다른 생성자를 호출할 수 있음 (이때 호출 코드 이전에 다른 코드를 넣으면 오류 발생)
- this를 활용해 생성된 클래스 자신의 주소값을 반환할 수 있음

### static 변수

- static 변수는 정적 변수 혹은 클래스 변수(class variable)라고도 함
- static 변수는 클래스에서 공통으로 사용하는 변수, 즉 프로그램이 실행되어 메모리에 올라갔을 때 한 번 메모리 공간이 할당되고, 그 후 모든 인스턴스가 공유하는 변수
- 자바에서는 다른 멤버 변수처럼 클래스 내부에, static 예약어를 사용하여 선언

아래는 static의 사용법이다.
```
static 자료형 변수명;
```

아래처럼 class 안에 static 예약어를 사용하여 선언한다.
```java
public class Student {
    public static int serialNum = 1000;
    public int studentID;
    public String studentName;
}
```

- static 변수는 인스턴스 생성과는 별개이므로 **인스턴스보다 먼저 생성**
- 따라서 static 변수는 클래스 이름으로도 참조하여 사용 가능 (보통 클래스 이름과 함께 사용)
- static 변수를 위한 메서드를 static 메서드 또는 클래스 메서드(class method)라고 함
- static 메서드 또한 static 변수처럼 클래스 이름으로 직접 호출 가능

아래는 static 메서드를 구현한 코드이다.

```java
public class Student2 {
    private static int serialNum = 1000;
    int studentID;
    String studentName;
    int grade;
    String address;

    public Student2() {
        serialNum++;
        studentID = serialNum;
    }

    public static int getSerialNum() {
        int i = 10;
        return serialNum;
    }

    public static void setSerialNum(int serialNum) {
        Student2.serialNum = serialNum;
    }
}
```

- static 메서드 내에서 지역 변수와 클래스 변수는 사용할 수 있지만, 인스턴스 변수를 사용하면 오류가 발생함

### 변수 유효 범위 (scope)

- 변수는 특성에 맞게 선언해서 사용하는 것이 중요함
- 지역 변수(local variable) : 함수/메서드 내부에서 선언하기 때문에 함수 밖에서는 사용 불가
- 멤버 변수(member variable) : 클래스의 어느 메서드에서나 사용 가능
- static 변수 : private이 아니라면 클래스 외부에서도 객체 생성과 무관하게 사용 가능

|변수 유형|선언 위치|사용 범위|메모리|생성과 소멸|
|--------|--------|---------|------|---------|
|지역 변수|함수 내부에 선언|함수 내부에서만 사용|스택|함수가 호출될 때 생성되고 함수가 끝나면 소멸|
|멤버 변수|클래스 멤버 변수로 선언|클래스 내부에서 사용, private이 아니면 다른 클래스에서 접근 가능|힙|인스턴스가 생성될 때 힙에 생성, 가비지 컬렉터가 메모리 수거 시 소멸|
|static 변수|static 예약어를 사용하여 클래스 내부에 선언|클래스 내부에서 사용, private이 아니면 클래스 이름으로 다른 클래스에서 사용 가능|데이터 영역|프로그램 시작 시 데이터 영역에 생성, 프로그램 종료와 메모리 해제 시 소멸|

- static 변수는 프로그램 시작부터 끝까지 메모리에 상주하므로, 크기가 너무 큰 변수를 static으로 선언하는 것은 좋지 않음
- 지역 변수 -> 함수에서 기능 구현을 위해 잠시 사용할 때
- 멤버 변수 -> 클래스의 속성을 나타내고, 각 인스턴스마다 다른 값을 가질 때
- static 변수 -> 여러 인스턴스에서 공유해서 사용, 한 번만 생성

### 싱글톤 패턴 (basic.singleton pattern)

- 싱글톤 패턴은 객체 지향 프로그램에서 **인스턴스를 단 하나**만 생성하는 디자인 패턴
- 실무 혹은 여러 프레임워크에서 많이 사용하는 패턴

참고) 디자인 패턴(design pattern)이란 객체 지향 프로그램을 어떻게 구현해야 더 유연하고 재활용성이 높은 프로그램을 만들 수 있는지 정리한 내용이다. 다시 말해, 프로그램 특성에 따른 설계 유형을 이론화한 것이다.

#### 1단계 : 생성자를 private으로 만들기
- private으로 디폴트 생성자를 명시하여, 외부 클래스에서 마음대로 인스턴스를 여러 개 생성하는 것을 막기 위해 
- 클래스 내부에서만 해당 클래스의 생성을 제어할 수 있음
```java
public class Company {
    private Company() {}
}
```

#### 2단계 : 클래스 내부에 static으로 유일한 인스턴스 생성
- 이 인스턴스가 프로그램 전체에서 사용할 유일한 인스턴스
- 유일한 인스턴스를 private으로 선언하여 인스턴스 오류 방지
```java
public class Company {
    private static Company instance = new Company();
    private Company() {}
}
```

#### 3단계 : 외부에서 참조 가능한 public 메서드 만들기
- 외부 사용이 가능하도록, 유일하게 생성한 인스턴스를 반환하는 public 메서드 생성
- 이때 인스턴스 생성과 상관없이 호출할 수 있어야 하기 때문에, 인스턴스 반환하는 메서드는 반드시 static으로 선언
```java
public class Company {
    private static Company instance = new Company();
    private Company() {}
    
    public static Company getInstance() {
        if(instance == null) {
            instance = new Company();
        }
        return instance;
    }
}
```

#### 4단계 : 클래스를 실제 사용하는 코드 만들기
- 외부 클래스에서는 객체를 생성할 수 없으므로, static으로 제공되는 getInstance() 메서드를 호출
```java
public class CompanyTest {
    public static void main(String[] args) {
        Company myCompany1 = Company.getInstance();
        Company myCompany2 = Company.getInstance();
        System.out.println(myCompany1 == myCompany2);
    }
}
```

### 배열

- 배열을 사용하면 자료형이 같은 자료 여러 개를 한 번에 관리 가능
- 배열 요소들은 자료형이 모두 같다.

아래는 배열의 선언 방법이다.
```
자료형[] 배열이름 = new 자료형[개수];
자료형 배열이름[] = new 자료형[개수];
```

- 기본적으로 배열의 자료형에 따라 정수는 0, 실수는 0.0, 객체 배열은 null로 초기화됨
- 배열을 특정한 값으로 초기화할 수도 있음
- 특정한 값으로 초기화하는 경우 `[]`안의 개수는 생략해야 함
- 선언과 동시에 초기화할 때 `new 자료형[]`부분 생략 가능 (선언 후 초기화할 때는 생략할 수 없음)

아래는 배열을 선언하고 특정한 값으로 초기화한 코드이다.
```java
int[] studentIDs = new int[] {101, 102, 103};
int[] studentIDs = {101, 102, 103};
```

- 배열은 배열 총 길이를 나타내는 length 속성을 가짐

아래는 배열을 사용하고 출력한 코드이다.
```java
public class ArrayTest {
    public static void main(String[] args) {
        int[] num = new int[] {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
        
        for(int i = 0; i < num.length; i++) {
            System.out.println(num[i]);
        }
    }
}
```

- 객체 배열을 선언하게 되면, 각각의 **인스턴스 주소 값을 담을 공간**이 생성됨
- 즉, Book이라는 클래스가 있다고 가정할 때 `Book[] library = new Book[5];`의 5개 공간에는 각각 Book 객체의 주소값을 담을 수 있음
- 아래 코드처럼 객체 배열 선언 후에 new 키워드를 사용하여 생성된 객체를 직접 저장해야 함

```java
public class BookArray {
    public static void main(String[] args) {
        Book[] library = new Book[5];

        library[0] = new Book("태백산맥", "조정래");
        library[1] = new Book("데미안", "헤르만 헤세");
        library[2] = new Book("어떻게 살 것인가", "유시민");
        library[3] = new Book("토지", "박경리");
        library[4] = new Book("어린 왕자", "생텍쥐페리");

        for(int i = 0; i < library.length; i++) {
            library[i].showBookInfo();
        }

        for(int i = 0; i < library.length; i++) {
            System.out.println(library[i]);
        }
    }
}
```

- 배열 복사는 기존 배열과 자료형, 배열 크기가 같은 배열을 새로 만들거나 더 큰 배열을 만들어 기존 배열 자료를 불러올 때 사용
- 배열 복사의 가장 단순한 방법은 for문을 활용한 복사임
- 다른 방법은 `System.arraycopy()`메서드를 사용하는 방법
- `System.arraycopy(src, srcPos, dest, destPos, length)`메서드의 각 매개변수 설명은 아래와 같음
- 복사할 대상 배열의 길이가 복사할 요소 개수보다 작다면 오류 발생

|매개변수|설명|
|-------|----|
|src|복사할 배열 이름|
|srcPos|복사할 배열의 첫 번째 위치|
|dest|복사해서 붙여 넣을 대상 배열 이름|
|destPos|복사해서 대상 배열에 붙여넣을 첫 번째 위치|
|length|src에서 dest로 복사할 요소 개수|

- 객체 배열의 요소에 저장된 값은 인스턴스 자체가 아니라 **인스턴스 주소값**
- 따라서 객체 배열 복사 시 배열 인스턴스 값 변경되면 두 배열 모두 영향 받음
- 이를 **얕은 복사**(shallow copy)라고 함
- 반대로, 인스턴스를 따로 관리하고 싶으면 직접 인스턴스를 만들고 그 값을 복사해야 함
- 이를 **깊은 복사**(deep copy)라고 함

### 다차원 배열

- 위의 배열은 모두 '일차원 배열'에 대한 설명임
- 이차원 이상으로 구현한 배열을 다차원 배열이라고 함
- 다차원 배열은 평면이나 공간 개념 구현에 사용

### 향상된 for문 (enhanced for loop)

- 배열의 처음에 끝까지 모든 요소를 참조할 때 사용하면 편리
- 배열 요소 값을 순서대로 가져와 하나씩 변수에 대입
- 모든 배열의 시작 요소부터 끝 요소까지 실행

아래처럼 사용할 수 있다.
```java 
for(자료형 변수 : 배열) {
  반복 실행문;
}
```

### 상속 (basic.inheritance)

- 객체지향 프로그래밍의 중요 특징 중 하나
- B 클래스가 A 클래스를 상속받으면, B 클래스는 A 클래스의 멤버 변수와 메서드를 사용할 수 있음
- 상속을 사용함으로써 **유지보수**하기 편하고 **프로그램 수정/내용 추가가 유연**함
- 상속하는 부모 클래스(parent class)는 '상위 클래스', 상속받는 자식 클래스(child class)는 '하위 클래스'라고 함
- 상속 관계에서는 하위 클래스가 상위 클래스보다 구체적인 클래스
- 자바 문법으로 상속을 구현할 때는 '연장, 확장하다'의 뜻을 가진 `extends` 예약어 사용
- 하위 클래스가 생성될 때 상위 클래스가 먼저 생성됨
- `super` 예약어를 사용하여 상위 클래스에 접근 가능 (하위 클래스 생성자에서 `super()` 자동 호출)
- 클래스 변경 시, 하위 클래스는 상위 클래스로 묵시적 형변환됨 (이 경우 상위 클래스의 변수와 메서드만 참조 가능)
- 자바는 다중 상속(한 클래스가 여러 클래스를 상속)을 지원하지 않음 (다중 상속으로 인한 모호성을 없애기 위해)

### 메서드 오버라이딩 (method overriding)

- 상위 클래스에 정의한 메서드가 하위 클래스에서의 구현과 맞지 않을 때, **하위 클래스에서 메서드를 재정의**하는 것
- 오버라이딩 시 반환형, 메서드 이름, 매개변수 개수, 매개변수 자료형이 같아야 함
- `@Override` 애노테이션은 재정의된 메서드임을 컴파일러에 명확히 알려줌

참고) 애노테이션은 영어로 주석이라는 의미로, `@애노테이션이름`으로 표현한다. 자바에서 제공하는 애노테이션은 컴파일러에게 특정한 정보를 제공해주는 역할을 한다. 미리 정의된 애노테이션을 **표준 애노테이션**이라고 한다. 아래는 표준 애노테이션의 예시이다.

|애노테이션|설명|
|--------|-----|
|@Override|재정의된 메서드라는 정보 제공|
|@FunctionalInterface|함수형 인터페이스라는 정보 제공|
|@Deprecated|이후 버전에서 사용되지 않을 수 있는 변수, 메서드에 사용|
|@SuppressWarnings|특정 경고가 나타나지 않도록 함|

### 가상 메서드 (virtual method)

- 자바의 모든 메서드는 가상메서드임
- 클래스를 사용하여 인스턴스를 생성하면 멤버 변수는 **힙 메모리**에 위치하고, 메서드는 **메서드 영역**에 위치함
- 인스턴스가 달라도 동일한 메서드 호출
- 일반적으로 메서드를 호출한다는 것은 그 메서드의 **명령 집합이 있는 메모리 위치를 참조**하여 명령을 실행하는 것
- 재정의된 메서드는 실제 인스턴스의 메서드 호출, 재정의되지 않은 메서드는 상위 클래스 메서드 호출 (후자는 호출하는 메서드 주소가 같음)

![가상메서드 예시 사진](https://media.vlpt.us/images/ldevlog/post/858b7c8e-641e-47fc-bb5f-d10488f7a84c/image.png)

### 다형성 (basic.polymorphism)

- 하나의 코드가 여러 자료형으로 구현되어 실행되는 것 (같은 코드에서 여러 실행 결과 나오는 것)
- 추상 클래스, 인터페이스에서 구현됨
- 묵시적 클래스 형 변환과 가상 메서드를 바탕으로 함
- 상위 클래스에서 **공통 부분의 메서드**를 제공하고, 하위 클래스에서 **추가 요소**를 덧붙여 구현
- 또는 상속받은 모든 클래스를 **하나의 상위 클래스로 처리**
- 다형성을 활용하여 유연하면서도 구조화되고, 확장성 있고 유지보수하기 좋은 프로그램 개발 가능

아래는 다형성을 활용한 코드이다.
```java
class Animal {
    public void move() {
        System.out.println("동물이 움직입니다.");
    }
}

class Human extends Animal {
    public void move() {
        System.out.println("사람이 두 발로 걷습니다.");
    }
}

class Tiger extends Animal {
    public void move() {
        System.out.println("호랑이가 네 발로 뜁니다.");
    }
}

class Eagle extends Animal {
    public void move() {
        System.out.println("독수리가 하늘을 납니다.");
    }
}

public class AnimalTest1 {
    public static void main(String[] args) {
        AnimalTest1 aTest = new AnimalTest1();
        aTest.moveAnimal(new Human());
        aTest.moveAnimal(new Tiger());
        aTest.moveAnimal(new Eagle());
    }

    public void moveAnimal(Animal animal) {
        animal.move();
    }
}
```

- 앞에서 봤듯이 상속을 사용하면 모든 등급에서 공통으로 사용하는 코드 부분은 상위 클래스에 구현하고, 각 등급별 내용은 각각의 하위 클래스에 구현
- 상속을 사용하는 것이 항상 좋은 것은 아님 (IS-A 관계일 때 사용하는 것이 가장 효율적, 일반 클래스를 점차 구체화하는 상황)
- 단순히 코드 재사용의 목적으로 **서로 관련이 없는 클래스를 상속 관계로 사용하는 것은 좋지 않음**

참고) `IS-A` 관계 : 일반적인 개념과 구체적인 관계 (is a relationship; basic.inheritance) <br />
참고) `HAS-A` 관계 : 한 클래스가 다른 클래스를 소유한 관계 (has a relationship; association), 이 경우 상속은 옳지 않음

### 다운 캐스팅 (down casting)

- 다운 캐스팅 : 상위 클래스로 형 변환되었던 하위 클래스를 다시 원래 자료형으로 형 변환하는 것
- `instanceof` : 자료형을 확인하는 키워드 (형변환하기 전 원래 인스턴스 자료형)
- 하위 클래스로 형변환 할 때는 명시적으로 해야 함

아래는 다운 캐스팅을 구현한 코드이다.
```java
Animal hAnimal = new Human();
if(hAnimal instanceof Human) {    // hAnimal 인스턴스 자료형이 Human형이라면
  Human human = (Human)hAnimal;   // 인스턴스 hAnimal을 Human형으로 다운 캐스팅
}
```

### 추상 클래스 (abstract class)

- 추상 클래스는 항상 추상 메서드(abstract method)를 포함
- 추상 메서드는 **구현 코드가 없음** (함수 몸체가 없음)
- 추상 메서드를 선언할 때는 `abstract` 예약어 사용
- 추상 메서드를 가진 추상 클래스에도 `abstract` 예약어 사용해야 함
- 함수의 구현부(implementation)(중괄호로 감싼 부분)
- 실제 추상 클래스는 많은 프레임워크에서 사용하고 있는 구현 방식

아래는 add라는 추상 메서드를 구현한 코드이다.
```java
abstract int add(int x, int y);
```

다음과 같이 ;가 아닌 {}를 사용한 메서드는 추상 메서드가 아니다. (함수 구현부가 비어있는 메서드를 구현한 것)
```java
int add(int x, int y) {}
```

- 추상 클래스를 상속받는 클래스에 **추상 메서드의 구현에 대한 책임을 위임**함
- 하위 클래스에서 공통으로 사용할 메서드는 일반 메서드, 하위 클래스마다 다르게 구현할 때는 추상 메서드로 선언
- 모든 메서드를 구현한 클래스에 `abstract` 예약어를 사용하여도 추상 클래스임 (완벽한 구현이 아닌 공통 기능만 구현한 클래스, 즉 상속만을 위해 만든 클래스는 추상 클래스로 만듦)
- 추상 클래스는 `new` 예약어로 인스턴스를 생성할 수 없음

|메서드|특징|
|------------|----------|
|구현된 메서드|하위 클래스에서 공통으로 사용할 구현 코드. 하위 클래스에서 재정의 가능|
|추상 메서드|하위 클래스가 어떤 클래스냐에 따라 구현 코드가 달라짐|

### 템플릿 메서드 (basic.template method)

- 디자인 패턴의 한 방법으로, 모든 객체지향 프로그램에서 사용하는 구현 방법
- **메서드 실행 순서**와 **시나리오**를 정의하는 메서드
- 하위 클래스에 따라 구현 내용이 바뀌는 것 말고, 변하지 않는 시나리오를 템플릿 메서드로 정의
- 템플릿 메서드는 시나리오를 정의한 메서드, 즉 공통으로 사용하는 메서드이므로 하위 클래스에서 재정의하면 안 됨 (그래서 `final` 예약어 사용)
- **로직 흐름이 이미 정해져 있는 프레임워크**에서 많이 사용하는 기본 구현 방법

```java
public abstract class Car {
    public abstract void drive();
    public abstract void stop();

    public void startCar() {
        System.out.println("시동을 켭니다.");
    }

    public void turnOff() {
        System.out.println("시동을 끕니다.");
    }

    // 템플릿 메서드
    final public void run() {
        startCar();
        drive();
        stop();
        turnOff();
    }
}
```

### final 예약어 

- `final` 예약어를 사용하면 더 이상 수정할 수 없다는 뜻
- 자바에서 `final` 예약어는 변수, 메서드, 클래스에 사용 가능
- 상수 선언 시 일반 변수와 구별하기 위해 대문자로 씀

|사용 위치|설명|
|-------|---|
|변수|final 변수는 상수를 의미|
|메서드|final 메서드는 하위 클래스에서 재정의 불가|
|클래스|final 클래스는 상속 불가|

```java
final double PI = 3.14;
System.out.println(PI);
PI = 1.23; // error
```

- 보안과 관련되어 있거나 기반 클래스가 변하면 안 되는 경우 클래스를 `final`로 선언
- 대표적으로 JDK에서 String, Integer 클래스 등이 `final`로 선언한 클래스

### 테스트 주도 개발 (Test Driven Development; TDD)

- **테스트 코드**를 먼저 개발하는 개발 방법론 (studentTest.java -> student.java)
- 이미 학습한 코드를 이해하면서 자기만의 코딩 가능
- 테스트 코드를 만들 수 있다는 것은 이미 구현 코드가 머릿속에 있다는 뜻

### 인터페이스 (interface)

- 동일한 목적 하에 **동일한 기능을 수행**하게 하는 것이 인터페이스의 역할
- 클래스 혹은 프로그램이 제공하는 기능을 **명시적으로 선언**
- 추상 메서드와 상수로 이루어짐
- 인터페이스 내의 메서드는 `public abstract` 예약어를 명시하지 않아도 컴파일 과정에서 **자동으로 추상메서드로 변환**
- 인터페이스 내에 선언한 변수는 컴파일 과정에서 **상수로 자동 변환됨**
- 자바의 다형성을 극대화하여 개발 코드 수정을 줄이고 프로그램 유지보수성을 높이기 위해 사용

```java
public interface Calc {
    double PI = 3.14;
    int ERROR = -99999999;

    int add(int num1, int num2);
    int substract(int num1, int num2);
    int times(int num1, int num2);
    int divide(int num1, int num2);
}
```

- `implements` : 클래스에서 인터페이스를 구현할 때 쓰는 키워드
- 인터페이스로는 `new`로 인스턴스를 생성할 수 없음

```java
public class LeastJob implements Scheduler {
    @Override
    public void getNextCall() {
        System.out.println("상담 전화를 순서대로 대기열에서 가져옵니다.");
    }

    @Override
    public void sendCallToAgent() {
        System.out.println("현재 상담 업무가 없거나 대기가 가장 적은 상담원에게 할당합니다.");
    }
}
```

- 자바 8부터는 인터페이스 활용성을 높이기 위해 **디폴트 메서드**와 **정적 메서드** 기능을 제공
- 디폴트 메서드 : 인터페이스에서 구현 코드까지 작성한 메서드 (인터페이스를 구현한 클래스에서 코드 구현할 필요 없음)
- 정적 메서드 : 인스턴스 생성과 상관없이 사용할 수 있는 메서드

---

## 기타 라이브러리

### 예외 처리

- 에러는 `컴파일 에러(compile error)`와 `실행 에러(runtime error)` 두 종류가 있음
- 실제 서비스의 경우에는 `실행 에러`가 생기면 서비스가 중지되므로 문제가 심각해짐
- 자바는 이러한 비정상 종료를 줄이기 위해 다양한 예외 처리 방법을 제공함
- 서비스가 운영 중인 경우 남긴 `로그(log)` 분석을 통해 원인을 찾을 수 있음

















