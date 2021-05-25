---
layout: single
title: "Python basic 2일차 (#2. 파이썬 자료형 및 연산자)"
description: "파이썬 베이직 2일차 공부한 내용을 코딩을 옮기고 간단한 설명을 덧붙였습니다."
headline: "파이썬 베이직 2일차"
categories: [Python basic]
tags: [python,data science, 데이터 분석, 머신러닝, 빅데이터]
comments: true
published: true
---

**"파이썬 베이직 2일차 공부한 내용(파이썬 개요 및 설치)을 코딩을 옮기고 간단한 설명을 덧붙였습니다."**


# 파이썬 3에서는 long형이 삭제되고 모두 int형으로 처리됩니다.


```python
type(1)
```




    int




```python
type(2**31)
# 2**31은 2의 31제곱을 의미합니다.
```




    int



# 실수를 표현하기 위한 float 형


```python
type(3.14)
```




    float




```python
type(314e-2)
# 3.14를 지수형으로 표현한 경우이다.
```




    float



# 실수보다 좀 더 큰 범위의 수인 복소수를 나타내고 사용하는 방법


```python
x= 3-4j
type (x)
```




    complex




```python
x.imag
# imag은 복소수의 허수부를 나타낸다.
```




    -4.0




```python
x.real
# real은 복소수의 실수부를 나타낸다.
```




    3.0




```python
x.conjugate()
#conjugate는 켤레복소수를 반환한다.
```




    (3+4j)



#  연산자 (원의 넓이,삼각형의 넓이 구하기)


```python
r = 2
circle_area = 3.14 * (r**2)
# 3.14*(r**2)의 값은 3.14 * r ** 2의 값과 같다. 그 이유는 **(거듭제곱)의 우선순위가 *(곱하기)보다 높기 때문이다.
# 하지만 가독성을 높이기 위하여 괄호를 쓰는 것이 좋다.
x= 3
y= 4
triangle_area = x * y / 2
print(circle_area,triangle_area)
```

    12.56 6.0
    

# 정수나누기(//) 연산자


```python
2 // 3
```




    0




```python
5 // 2
```




    2




```python
# 정수나누기 연산자를 사용하면 나누고 난 후의 정수 부분만을 결과로 취한다.
```

# 문자열 ('' / "")


```python
'string'
```




    'string'




```python
"string"
```




    'string'




```python
"This is 'string'"
```




    "This is 'string'"




```python
type('string')
```




    str




```python
# 파이썬에서 문자를 '' 또는 ""로 묶어서 표현한다. 반드시 시작한 인용부호로 끝맺음을 지어야한다.
```

# 문자열(""")


```python
print("""영원에 살고 순간에 살아라. 영원리 살 것처럼 일하고
금방 죽을것처럼 사람들을 대하라.
            - 리히첸베르크""")
# 쉽게 다량의 문자열을 쉽게 넣기위해서 """ """이 사용되며, 줄바꿈이나 탭도 그대로 적용된다.
```

    영원에 살고 순간에 살아라. 영원리 살 것처럼 일하고
    금방 죽을것처럼 사람들을 대하라.
                - 리히첸베르크
    


```python
print(""영원에 살고 순간에 살아라. 영원리 살 것처럼 일하고
금방 죽을것처럼 사람들을 대하라.
            - 리히첸베르크"")
#""은 신택스 오류가 발생한다.
```


      File "<ipython-input-25-3fc54c8927cb>", line 1
        print(""영원에 살고 순간에 살아라. 영원리 살 것처럼 일하고
                ^
    SyntaxError: invalid syntax
    


# 이스케이프 문자를 사용하여 문자열 내에서 줄바꿈이나 탭등의 특수문자 사용하기

|사용 예|의미|
|------|---|
|\n|줄바꿈|
|\t|탭|
|\r|캐리지 반환|
|\0|널(null)|
|\\|문자(\)|
|\'|단일 인용부호(')|
|\"|이중 인용부호(")|


```python
print("\t탭\n다음줄")
```

    	탭
    다음줄
    


```python
print(r"\t탭\n다음줄")
# 문자열 앞에 r을 붙여서 로(raw) 문자열로 선언할 수 있다. r을 붙이게 되면 이스케이프 문자가 적용되지 않는다.
```

    \t탭\n다음줄
    

# 문자열 연산자


```python
'py''thon'
# (+)는 문자열 상수끼리는 생략할 수 있다.
```




    'python'




```python
'py'+'thon'
```




    'python'




```python
'py' * 3
# (*)는 문자열을 반복시킬 수 있다.
```




    'pypypy'



# 문자열 인덱싱


```python
a = "python"
a[0]
# 파이썬은 인덱싱이 가능하여 변수 뒤에 [위치]를 붙여서 원하는 문자를 꺼낼 수 있다. 제일 첫 문자의 위치는 0이다.
```




    'p'




```python
a[5]
```




    'n'




```python
a[0] = "a"
# 단, 인덱싱을 이용한 문자열의 변경은 허용하지 않는다. 다만 문자열 전체를 다시 할당할 때는 가능하다.
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-46-d6f8c36ea6ff> in <module>
    ----> 1 a[0] = "a"
    

    TypeError: 'str' object does not support item assignment



```python
#+---+---+---+---+---+
#|p|y|t|h|o|n|
#+---+---+---+---+---+
# 0 1 2 3 4 5 6
# -6 -5 -4 -3 -2 -1
# 0은 첫 문자의 바깥 부분을 가리키며, 증가하면 오른쪽으로 한 칸씩 이동한다. 음수를 지정하면 문자열 끝에서부터 동일하게 세어나간다.
```


```python
a[0:1]
```




    'p'




```python
a[1:4]
# 문자열을 인덱스를 통해 꺼내는 것을 슬라이싱(slicing)이라고 하며 변수 뒤에 [시작위치:끝위치]를 붙여서 원하는 문자열을 꺼낼 수 있다.
```




    'yth'




```python
a[:2]
```




    'py'




```python
a[-2:]
```




    'on'




```python
a[:]
# 위치를 생략한 경우에는 문자열의 처음이나 끝으로 간주한다.
```




    'python'




```python
a[::2]
# 증가 여부를 나타내는 인자를 생략하면 1로 간주되어 하나씩 증가시키게 된다.
```




    'pto'



# 문자열이나 수치 간의 변환


```python
str(3.14)
```




    '3.14'




```python
int(49)
```




    49




```python
float(23)
# 문자열이나 수치 간의 변환은 각 타입 클래스의 생성자를 이용하면 가능하다.
```




    23.0



# 리스트


```python
colors = ['red', 'green', 'gold']
colors
# 리스트는 값의 나열이다. 순서가 존재하며, 여러 종류의 값을 담을 수 있으며, 인덱스가 있고 슬라이싱도 가능하다.
```




    ['red', 'green', 'gold']




```python
type(colors)
```




    list




```python
colors.append('blue')
colors
# append()를 사용하면 삽입된 값이 리스트 맨 뒤에 추가된다.
```




    ['red', 'green', 'gold', 'blue']




```python
colors.insert(1,'black')
colors
#insert()를 사용하면 매서드의 첫 번째 인자에 원하는 위치를 지정한 후 두 번째 인자에 원하는 값을 넣는다.
```




    ['red', 'black', 'green', 'gold', 'blue']




```python
colors.extend(['white','gray'])
colors
# extend() 메서드를 이용하면 원하는 튜플이나 리스트등의 여러 값을 한번에 삽입할 수 있다.
```




    ['red', 'black', 'green', 'gold', 'blue', 'white', 'gray']




```python
colors +=['red']
colors
```




    ['red', 'black', 'green', 'gold', 'blue', 'white', 'gray', 'red']




```python
colors += 'red'
colors
# 리스트에서는 더하기(+) 연산자를 지원한다. 더하기 연산자를 사용할 경우, 
# extend() 메서드와 마찬가지로 순회가능한 리스트,튜플 등의 값을 넣어야한다.
```




    ['red',
     'black',
     'green',
     'gold',
     'blue',
     'white',
     'gray',
     'red',
     'r',
     'e',
     'd']




```python
colors.index('red')
# index() 메서드의 결과는 처음 찾은 값만 반환하므로, 0이 나온다.
```




    0




```python
colors.index('red',1)
# index()의 두 번째 인자로 시작점을 명시하면 7이 결과로 나온다.
```




    7




```python
colors.index('red',1,5)
# 원하는 값이 없을 때는 아래와 같이 오류가 나온다.
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-31-928b8b5fcf56> in <module>
    ----> 1 colors.index('red',1,5)
    

    ValueError: 'red' is not in list



```python
colors
```




    ['red', 'black', 'green', 'gold', 'blue', 'white', 'gray', 'red']




```python
colors.count('red')
# 해당 값의 개수를 반환하는 count() 메서드
```




    2




```python
colors.pop()
colors
# 2번 실행해서 gray와 red를 제거함
```




    ['red', 'green', 'gold', 'blue', 'white']




```python
colors.pop(1)
```




    'black'




```python
colors
# pop() 메서드의 인자를 생략하면 뒤에서 값을 뽑아내며, 원하는 위치를 인자로 제공할 수 있다. pop되면 해당 리스트에서 삭제된다.
```




    ['red', 'green', 'gold', 'blue', 'white', 'gray']




```python
colors.remove('gold')
colors
# remove는 pop과 다르게 해당 값을 삭제합니다. 동일한 값이 2개가 있다면 앞 쪽에 있는 값부터 제거한다.
```




    ['red', 'green', 'blue', 'white']




```python
colors.sort()
colors
# sort() 메서드를 사용하면 순방향 정렬이 된다.
```




    ['blue', 'green', 'red', 'white']




```python
colors.reverse()
colors
# reverse() 메서드를 사용하면 역방향 정렬이 된다.
```




    ['white', 'red', 'green', 'blue']




```python
def mysort(x):
    return x[-1]
colors.sort(key=mysort)
# sort 메서드는 자신이 원하는 방식으로 정렬할 수 있는데 key값을 지정하여 정렬 방식을 조정할 수 있다. 위의 경우 마지막 문자를 기준으로 비교한다.
```


```python
colors
```




    ['red', 'white', 'blue', 'green']




```python
colors.sort(key=mysort, reverse = True)
# reverse 여부 또한 지정할 수 있다.
```


```python
colors
```




    ['green', 'white', 'blue', 'red']



# 세트


```python
a = {1,2,3}
b = {3,4,5}
```


```python
a
```




    {1, 2, 3}




```python
b
```




    {3, 4, 5}




```python
type(a)
# 세트는 리스트와 동일하게 값의 모임이며 순서는 없다.
```




    set




```python
a.union(b) # 합집합
# 제공되는 메서드는 리스트와 거의 유사하며, 합집합과 교집합을 구할 수 있다.
```




    {1, 2, 3, 4, 5}




```python
a.intersection(b) # 교집합
```




    {3}




```python
a - b # 차집합
```




    {1, 2}




```python
a | b # 합집합
```




    {1, 2, 3, 4, 5}




```python
a & b #교집합
```




    {3}



# 튜플


```python
t = (1,2,3)
t
```




    (1, 2, 3)




```python
type(t)
# 튜플은 리스트와 유사하지만, 리스트와는 달리 []대신 ()로 묶어서 표현하며, 읽기 전용이다. 읽기 전용인 만큼 함수도 리스트에 비해 적지만 
# 속도가 빠르다.
```




    tuple




```python
t.count(1)
```




    1




```python
t.index(3)
# 튜플이 제공하는 함수는 count(),index() 뿐이다.
```




    2




```python
a, b = 1, 2
```


```python
print(a,b)
```

    1 2
    


```python
(a,b) = (1,2)
print(a,b)
# 여러 값을 다중 할당 하는 것도 튜플이 생략된 것이라고 볼 수 있다.
```

    1 2
    


```python
a, b = 1, 2
```


```python
print(a,b)
```

    1 2
    


```python
(a,b) = (b,a)
```


```python
print(a,b)
# C와 같은 언어에서는 변수가 하나 더 필요한 swap예제를 이와 같이 표현할 수 있다.
```

    2 1
    


```python
a = set((1,2,3))
```


```python
a
```




    {1, 2, 3}




```python
type(a)
```




    set




```python
b = list(a)
```


```python
b
```




    [1, 2, 3]




```python
type(b)
```




    list




```python
c= tuple(b)
```


```python
c
```




    (1, 2, 3)




```python
type(c)
```




    tuple




```python
d = set(c)
```


```python
d
```




    {1, 2, 3}




```python
type(d)
# 리스트,세트,튜플은 다음과 같이 생성자 list(),set(),tuple()을 이용해 서로서로 언제든지 변환이 가능하다.
```




    set




```python
a = set((1,2,3))
1 in a
```




    True




```python
b = list(a)
2 in  b
```




    True




```python
c = tuple(b)
3 in c
```




    True




```python
4 in a
# 또한, 이 자료형들은 in 연산자가 동일하게 적용된다.
```




    False



# 사전


```python
d= dict(a=1,b=3,c=5)
d
```




    {'a': 1, 'b': 3, 'c': 5}




```python
type(d)
# 사전은 강력하면서도 알아두면 편리한 자료구조이다. 사전은 키와 값의 쌍으로 구성되어 있다.
```




    dict




```python
color = {"apple":"red","banana":"yellow"}
color
```




    {'apple': 'red', 'banana': 'yellow'}




```python
color["apple"]
```




    'red'




```python
color[0]
# dict() 생성자를 사용하지 않고 이와 같이 직접 사전을 생성할 수 있다. 인덱스는 사용하지 않으며, 없는키를 사용하면 에러가 발생한다.
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-121-b53403da2cb2> in <module>
    ----> 1 color[0]
    

    KeyError: 0



```python
color["cherry"] = "red"
```


```python
color
# 사전에 새로운 값을 추가하려면 위와 같이 새로운 키와 값을 할당하면 된다.
```




    {'apple': 'red', 'banana': 'yellow', 'cherry': 'red'}




```python
color["apple"] = "green"
```


```python
color
# 사전에 새로운 값을 변경하려면 항목의 키에 변경할 값을 할당하면 된다.
```




    {'apple': 'green', 'banana': 'yellow', 'cherry': 'red'}




```python
for c in color.items():
    print(c)
```

    ('apple', 'green')
    ('banana', 'yellow')
    ('cherry', 'red')
    


```python
for k,v in color.items():
    print(k,v)
```

    apple green
    banana yellow
    cherry red
    


```python
for k in color.keys():
    print(k)
```

    apple
    banana
    cherry
    


```python
for v in color.values():
    print(v)
# items()는 모든 키와 값을 튜플로 묶어 반환하며, keys()는 키만 values()는 값만 반환한다.
```

    green
    yellow
    red
    


```python
color
```




    {'apple': 'green', 'banana': 'yellow', 'cherry': 'red'}




```python
del color['cherry']
```


```python
color
# 'del'문을 이용하여 하나씩 삭제할 수 있다.
```




    {'apple': 'green', 'banana': 'yellow'}




```python
color.clear()
```


```python
color
# clear() 메서드를 이용하여 한번에 모두 삭제할 수 있다.
```




    {}




```python
{'age':40.5,'job':[1,2,3],'name':{'Kim':2, 'Cho':1}}
# 자료형을 섞어서도 사용 가능하다.
```




    {'age': 40.5, 'job': [1, 2, 3], 'name': {'Kim': 2, 'Cho': 1}}



# 부울


```python
isRight = False
```


```python
type(isRight)
#부울은 참과 거짓을 나타내는 자료형이다.
```




    bool




```python
1 < 2
```




    True




```python
1 != 2
```




    True




```python
1 == 2
# 부울은 부울 값들 간의 논리연산이나, 수치 간의 비교연산의 결과로 사용된다.
# 비교연산자의 종류는 >(크다),<(작다),==(같다),!=(다르다),>=(같거나 크다),<=(같거나 작다)
```




    False




```python
True and False
```




    False




```python
True & True
# and(&)는 두 값이 모두 참이여만 참을 반환한다.
```




    True




```python
True or False
```




    True




```python
False | False
# or(|) 하나의 값만 참이여도 참을 반환한다.
```




    False




```python
not True
# not은 반대되는 값을 반환한다.
```




    False




```python
bool(0)
# 수치를 논리연산자에 사용하는 경우,0은 False로 간주한다.
```




    False




```python
bool(-1)
# 음수를 포함한 다른 값은 True로 간주한다.
```




    True




```python
bool('test')
# 문자열을 논리연산자에 사용하는 경우에도 ''(빈 문자열)만 False로 본다.
```




    True




```python
bool(None)
# 값이 없는 상태의 None의 경우도 False로 본다.
```




    False



# 얕은 복사와 깊은 복사


```python
a = [1,2,3]
```


```python
b = a
```


```python
a[0] = 38
```


```python
a
```




    [38, 2, 3]




```python
b
# a에는 [1,2,3]의 주소가 저장돼 있으므로 b에도 a와 동일한 주소가 복사된다.
```




    [38, 2, 3]




```python
id(a),id(b)
# 객체의 고유한 값인 아이디를 반환하는 함수인 id()를 확인해 보면 더욱 확실해진다.
```




    (1697772933824, 1697772933824)




```python
a = [1,2,3]
```


```python
b = a[:]
```


```python
id(a),id(b)
```




    (1697772047808, 1697772922752)




```python
a[0] = 38
```


```python
a
```




    [38, 2, 3]




```python
b
# a와 b가 같은 개체를 공유하지 않게 하려면 이와 같이 강제로 복사하면 된다.
```




    [1, 2, 3]




```python
import copy
```


```python
a = [1,2,3]
```


```python
b = copy.deepcopy(a)
```


```python
a[0] = 38
```


```python
a
```




    [38, 2, 3]




```python
b
# 리스트 이외의 일반적인 경우에는 copy 모듈을 사용한다.
# copy()함수는 주소가 복사되어 객체를 공유하는 얕은 복사를 하는 함수이다.
#deepcopy()함수는 객체를 공유하지 않는 깊은 복사를 한다.
```




    [1, 2, 3]




```python

```
