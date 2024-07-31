# 문제

### 1. 아래는 C언어의 2차원 배열 형태이다. field의 경우 2차원 배열 형태는 예시처럼 출력되므로, 이를 참고하여 mines의 2차원 배열 형태를 작성하시오.

```c
#include <stdio.h>

void main()
{
    int field[4][4] = {{0, 1, 0, 1}, {0, 0, 0, 1}, {1, 1, 1, 0}, {0, 1, 1, 1}};
    int mines[4][4] = {{0, 0, 0, 0}, {0, 0, 0, 0}, {0, 0, 0, 0}, {0, 0, 0, 0}};

    int w = 4, h = 4;

    for (int y = 0; y < h; y++)
    {
        for (int x = 0; x < w; x++)
        {
            if (field[y][x] == 0)
                continue;

            for (int i = y - 1; i <= y + 1; i++)
            {
                for (int j = x - 1; j <= x + 1; j++)
                {
                    if (calculate(w, h, j, i) == 1)
                    {
                        mines[i][j] += 1;
                    }
                }
            }
        }
    }
    for (int y = 0; y < h; y++)
    {
        for (int x = 0; x < w; x++)
            printf("%d", mines[y][x]);
        printf("\n");
    }
}

int calculate(int w, int h, int j, int i)
{
    if (i >= 0 && i < h && j >= 0 && j < w)
        return 1;
    return 0;
}
```

#### 예시와 정답칸

<table>
  <tr>
    <td>
      <b>예시</b>
      <table border="1">
        <tr><td>0</td><td>1</td><td>0</td><td>1</td></tr>
        <tr><td>0</td><td>0</td><td>0</td><td>1</td></tr>
        <tr><td>1</td><td>1</td><td>1</td><td>0</td></tr>
        <tr><td>0</td><td>1</td><td>1</td><td>1</td></tr>
      </table>
    </td>
    <td>
      <b>정답칸</b>
      <table border="1">
        <tr><td>-</td><td>-</td><td>-</td><td>-</td></tr>
        <tr><td>-</td><td>-</td><td>-</td><td>-</td></tr>
        <tr><td>-</td><td>-</td><td>-</td><td>-</td></tr>
        <tr><td>-</td><td>-</td><td>-</td><td>-</td></tr>
      </table>
    </td>
  </tr>
</table>

<br />

### Solution

<details>
<summary> &nbsp; 확인하기</summary>
<div style="padding-left: 1rem" markdown="1">

요약 - 4\*4 지뢰찾기
<br />
<br />

**주요 코드**

```c
// 0 <= i < h, 0 <= j < w  이면 1 아니면 0리턴
int calculate(int w, int h, int j, int i)


// 4중 for문
// --- field 순회 ---
// 1. 0 < y < h  - y++
// 2. 0 < x < w  - x++
// field[y][x] == 1인 경우에만 아래의 for문 실행

// --- mines 순회 ---
// 3. y - 1 < i < y + 1  - i++
// 4. x - 1 < j < x + 1  - j++
// calculate(4, 4, j, i)가 1인 경우 -> mines[i][j] += 1;

// calculate는 i,j가 0과 3 사이에 있으면 1이므로
// -> field[y][x]가 1인 점의 플마 1의 점까지를 +1 시키면 됨.
// -> field[y][x]가 1인 점을 주변으로 +1 시키면 헷갈리니, 본인의 점을 반경으로 1의 갯수를 세는 것이 헷갈리지 않고 편함
for (int y = 0; y < h; y++)
    for (int x = 0; x < w; x++)
        for (int i = y - 1; i <= y + 1; i++)
            for (int j = x - 1; j <= x + 1; j++)
```

## 예시와 정답칸

<table>
  <tr>
    <td>
      <b>field</b>
      <table border="1">
        <tr><td>0</td><td>1</td><td>0</td><td>1</td></tr>
        <tr><td>0</td><td>0</td><td>0</td><td>1</td></tr>
        <tr><td>1</td><td>1</td><td>1</td><td>0</td></tr>
        <tr><td>0</td><td>1</td><td>1</td><td>1</td></tr>
      </table>
    </td>
    <td>
      <b>mines(정답)</b>
      <table border="1">
        <tr><td>1</td><td>1</td><td>3</td><td>2</td></tr>
        <tr><td>3</td><td>4</td><td>5</td><td>3</td></tr>
        <tr><td>3</td><td>5</td><td>6</td><td>4</td></tr>
        <tr><td>3</td><td>5</td><td>5</td><td>3</td></tr>
      </table>
    </td>
  </tr>
</table>

</div>
</details>
