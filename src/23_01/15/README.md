# 문제

### 15. 다음 파이썬 코드의 알맞는 출력값을 작성하시오.

```python
a = {'한국', '중국', '일본'}
a.add('베트남')
a.add('중국')
a.remove('일본')
a.update({'홍콩', '한국', '태국'})
print(a)
```

<br />

### Solution

<details>
<summary> &nbsp; 확인하기</summary>
<div style="padding-left: 1rem" markdown="1">

요약 - set 자료형, 내장 메서드 사용법
<br />
<br />

**개념**

```python
# 1. 리스트 [] / set {} / 튜플 () / 딕셔너리 {key: value}
# 2. 중괄호에 key,value가 없으므로 -> set 자료형임.
# 3. set은 중복 허용 x
# 4. add 추가 / remove 삭제 / update 여러개 추가.
```

**주요 코드**

```python
# set 함수 -> 중복 x
a = {'한국', '중국', '일본'}

# 베트남, 중국 추가
a.add('베트남')
a.add('중국')

# 일본 제거
a.remove('일본')

# 홍콩, 한국, 태국 추가 (update)
a.update({'홍콩', '한국', '태국'})

# 출력 -> {'한국', '중국', '베트남', '홍콩', '태국'}
print(a)
```

</div>
</details>
