# 문제

### 17. 다음 JAVA 코드에서 알맞는 출력 값을 작성하시오.

```JAVA
abstract class Vehicle {
    String name;
    abstract public String getName(String val);

    public String getName() {
        return "Vehicle name: " + name;
    }
}

class Car extends Vehicle {
    public Car(String val) {
        name=super.name=val;
    }
    public String getName(String val) {
        return "Car name:" + val;
    }
    public String getName(byte val[]) {
        return "Car name:" + val;
    }
}

public class Main {
    public static void main(String[] args) {
        Vehicle obj = new Car("Spark");
        System.out.println(obj.getName());
    }
}
```

<br />

### Solution

<details>
<summary> &nbsp; 확인하기</summary>
<div style="padding-left: 1rem" markdown="1">

요약 - 클래스, 상속, super, 추상 클래스, 오버라이딩 / 오버로딩
<br />
<br />

**개념**

```JAVA
추상 클래스 - abstract 키워드 이용 껍데기만 생성 가능, 상속받아 구현
```

**주요 코드**

```JAVA
// Car 클래스 인스턴스 생성
Vehicle obj = new Car("Spark");

// name과 super.name에 val(Spark) 추가
public Car(String val) {
    name=super.name=val;
}

// Vehicle에 정의된 getName() 메서드 실행 후 출력
System.out.println(obj.getName());

// 정답: Vehicle name: Spark
```

</div>
</details>
