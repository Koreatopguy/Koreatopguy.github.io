---
layout: page
title: "Python basic 1일차 (#1.파이썬 개요 및 설치)"
description: "파이썬 베이직 1일차 공부한 내용을 코딩을 옮기고 간단한 설명을 덧붙였습니다."
headline: "파이썬 베이직 1일차"
categories: python
tags: [python,data science, 데이터 분석, 머신러닝, 빅데이터]
comments: true
published: true
---

**"파이썬 베이직 1일차 공부한 내용(파이썬 개요 및 설치)을 코딩을 옮기고 간단한 설명을 덧붙였습니다."**

# 1. Hello world 출력하기


```python
print ("Hello world")
```

    Hello world


# 2. 위 소스 코드를 실행하면 hello world가 동일하게 출력되며 다른 프로그램에서 이 모듈을 불러왔을때 실행되지않음 



```python
if __name__ == "__main__":
    print ("Hello world")
```

    Hello world


# 들여쓰기는 하위 레벨의 코드블럭이 나오기전 : 또는 ; 가 나와야 하며, 들여쓰기는 스페이스 바 또는 탭을 활용해야한다.


```python
a = 1
if a == 1:
    print(1)
# 1번의 탭을 이용했을 경우
else:
 print(0)
#1번의 스페이스 바를 이용했을 경우
```

    1


# 같은 레벨의 코드 블록이나 상위레벨의 코드블록의 들여쓰기가 같지않으면 에러가 발생함.


```python
a = 1
if a == 1:
    print(1)
 print(0)
# 같은 레벨의 코드 블록이나 상위 레벨의 코드블록의 들여쓰기가 같지않음 (1 tab / 1 space)
```


      File "<tokenize>", line 4
        print(0)
        ^
    IndentationError: unindent does not match any outer indentation level



# 예외적으로 1줄짜리 간단한 하위 레벨은 같은 줄로 표현이 가능하다.


```python
a = 1
if a == 1: print(1)
```

    1



```python
a = 1
if a == 1: print(1); print(0) 
```

    1
    0


# ;을 붙이지 않아도 동일하게 작동함


```python
a = 1
b = 2;
```

# 한 라인에 여러 구문이 올때는 ;을 사용함 (:은 안됨)


```python
a = 1; b = 2
```

# 파이썬에서는 대소문자를 구분한다. 


```python
friend = 1
Friend = 10
print(friend)
print(Friend)
```

    1
    10


# for는 예약어 이므로 변수로 지정할 수 없다.


```python
for = 1
```


      File "<ipython-input-15-b26be1b49601>", line 1
        for = 1
            ^
    SyntaxError: invalid syntax



# 튜플, 리스트 사용, 다중 치환 


```python
(a,b) = (1,2)
# 튜플 사용
[c,d] = [3,4]
#리스트 사용
e = f = g = 1
#다중 치환
```

# int는 정수를 의미하고, 위와 같은 정수를 쓰면 10진수 정수로 인식합니다.


```python
year = 2008
month = 12
print(year,month)
```

    2008 12


# 0o -  8진수 0x - 16진수 0b - 2진수


```python
0o10
```




    8




```python
0x10
```




    16




```python
0b10
```




    2



# 10진수로 입력받아 각각 8진수 16진수 2진수로 변환하는 함수이다. 출력결과가 문자열임에 조심한다.


```python
oct(38)
```




    '0o46'




```python
hex(38)
```




    '0x26'




```python
bin(38)
```




    '0b100110'


