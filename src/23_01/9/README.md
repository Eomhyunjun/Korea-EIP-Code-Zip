# 문제

### 9. 다음 아래 코드에서 이진수를 십진수로 변환하는 코드에 대해 괄호 (a) (b)의 적합한 답을 작성하시오.

```C
#include <stdio.h>

int main() {

    int input = 101110;
    int di = 1;
    int sum = 0;

    while (1) {

        if (input == 0) break
        else {

          sum = sum + (input (a)(b)) * di;
             di = di * 2;
             input = input / 10;

        }
    }

    printf("%d", sum);

    return 0;
}
```

<br />
<br />

### Solution

<details>
<summary> &nbsp; 확인하기</summary>
<div style="padding-left: 1rem" markdown="1">

요약 - 이진수를 십진수로 변환하는 프로그램.
<br />
<br />

**주요 코드**

```C
input = input / 10; // 맨 뒷자리부터 10으로 나누어가며 10진수로 변환.
di = di \* 2; // 2진수의 자리수를 나타내기 위해 2를 곱해줌.
```

**문제 부분**

```C
sum = sum + (input(a)(b)) * di;

/*
* 1. sum은 결과 값.
* 2. sum에 (input(a)(b)) * di를 더해주고 있음.
* 3. (input(a)(b))는 input의 맨 뒷자리 숫자를 꺼내줘야 함.
* 4. 맨 뒤 숫자를 꺼내는 방법 -> input % 10;

* 정답 : a = %, b = 10;
*/
```

</div>
</details>
