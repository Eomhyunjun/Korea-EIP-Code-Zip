# 문제

### 20. 다음 자바 코드에 대한 출력 값을 작성하시오.

```JAVA
class Parent {
    int x = 100;

    Parent() {
        this(500);
    }

    Parent(int x) {
        this.x = x;
    }

    int getX() {
        return x;
    }
}

class Child extends Parent {
    int x = 4000;

    Child() {
        this(5000);
    }

    Child(int x) {
        this.x = x;
    }
}

public class Main {
    public static void main(String[] args) {
        Child obj = new Child();
        System.out.println(obj.getX());
    }
}
```

<br />

### Solution

<details>
<summary> &nbsp; 확인하기</summary>
<div style="padding-left: 1rem" markdown="1">

요약 - 클래스 생성자 호출
<br />
<br />

**주요 코드**

```JAVA
// 1. Child 인스턴스 생성
Child obj = new Child();

// 2. 기본 생성자 호출 -> this(5000) 호출
Child() {
    this(5000);
}

// 3. this(5000)이므로 Child(int x) 생성자 호출
//     -> child의 x = 5000
Child(int x) {
    this.x = x;
}

// 4. Parent 기본 생성자 호출 -> this(500) 호출
Parent() {
    this(500);
}

// 5. this(500)이므로 Parent(int x) 생성자 호출
Parent(int x) {
    this.x = x;
}


// 6. getX()는 Parent 클래스 밖에 없음.
//     -> Parent의 x 리턴 후 출력
System.out.println(obj.getX());

// 정답: 500
```

</div>
</details>
