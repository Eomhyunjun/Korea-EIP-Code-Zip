# 문제

### 14. 다음 코드에서 괄호안에 알맞는 값을 변수명으로 작성하시오.

```C
#include <stdio.h>

void swap(int *a, int idx1, int idx2)
{
    int t = a[idx1];
    a[idx1] = a[idx2];
    a[ (1) ] = t;
}

void Usort(int *a, int len)
{
    for (int i = 0; i < len - 1; i++)
        for (int j = 0; j < len - 1 - i; j++)
            if (a[j] > a[j + 1])
                swap(a, j, j + 1);
}

void main()
{
    int a[] = {85, 75, 50, 100, 95};
    int nx = 5;
    Usort(a, (2) );
}
```

<br />
<br />

### Solution

<details>
<summary> &nbsp; 확인하기</summary>
<div style="padding-left: 1rem" markdown="1">

요약 - 버블 정렬
<br>

**주요 코드**

```C
// a의 idx1과 idx2를 교환하는 함수
void swap(int *a, int idx1, int idx2)

// 이중 반복문을 돌며 a[j] > a[j+1] 인 경우 swap 함수 호출
void Usort(int *a, int len)

```

**문제 부분**

```C
void swap(int *a, int idx1, int idx2)
{
    int t = a[idx1];
    a[idx1] = a[idx2];
    a[(1)] = t;
}

/**
* 1. swap함수는 idx1과 idx2의 값 교환
* 2. a[(1)] = t; 는 idx2에 t값을 넣어줘야 함.

* 1번 정답 - idx2
*/

void main()
{
    int a[] = {85, 75, 50, 100, 95};
    int nx = 5;
    Usort(a, (2) );
}
/**
 * 1. Usort에 들어갈 len을 넣어주면 됨.
 * 2. len은 a의 길이 5이다.
 * 3. 변수명으로 작성하라 했으므로 정답은 nx
 *
 * 2번 정답: nx
*/


```

</div>
</details>
