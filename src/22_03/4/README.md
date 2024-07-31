# 문제

### 4. 아래 코드에 대한 출력 값을 작성하시오.

```c
#include <stdio.h>

void main()
{
    int result[5] = {};
    int arr[5] = {77, 32, 10, 99, 50};

    for (int i = 0; i < 5; i++)
    {
        result[i] = 1;
        for (int j = 0; j < 5; j++)
        {
            if (arr[i] < arr[j])
                result[i]++;
        }
    }

    for (int k = 0; k < 5; k++)
    {
        printf("%d", result[k]);
    }
}
```

<br />

### Solution

<details>
<summary> &nbsp; 확인하기</summary>
<div style="padding-left: 1rem" markdown="1">

요약 - 숫자 크기 순위 매기기
<br />
<br />

**주요 코드**

```c
// 2중 for문을 돌며 i < j인 경우 -> result[i]++;
for (int i = 0; i < 5; i++)
    for (int j = 0; j < 5; j++)

// 정답: 24513
```
