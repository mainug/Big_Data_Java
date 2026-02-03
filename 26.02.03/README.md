## 문자열 자료형


```python
str1 = "a" + "b"
str2 = "a 'b' c"
str3 = 'a "b" c'
str4 = """저는
여러줄을
작성합니다"""
str5 = '''
저는
여러줄을
작성합니다
'''
str6 = "저는\n여러줄을\n작성합니다"
str7 = "저는\"여러줄을\"작성합니다"

print(str1)
print(str2)
print(str3)
print(str4)
print(str5)
print(str6)
print(str7)
```

    ab
    a 'b' c
    a "b" c
    저는
    여러줄을
    작성합니다
    
    저는
    여러줄을
    작성합니다
    
    저는
    여러줄을
    작성합니다
    저는"여러줄을"작성합니다


<table style="float:left">
<thead>
<tr>
<th>코드</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>\n</code></td>
<td><mark>문자열 안에서 줄을 바꿀 때 사용</mark></td>
</tr>
<tr>
<td><code>\t</code></td>
<td>문자열 사이에 탭 간격을 줄 때 사용</td>
</tr>
<tr>
<td><code>\\</code></td>
<td><code>\</code>를 그대로 표현할 때 사용</td>
</tr>
<tr>
<td><code>\'</code></td>
<td>작은따옴표(')를 그대로 표현할 때 사용</td>
</tr>
<tr>
<td><code>\"</code></td>
<td>큰따옴표(")를 그대로 표현할 때 사용</td>
</tr>
<tr>
<td><code>\r</code></td>
<td>캐리지 리턴(줄 바꿈 문자, 커서를 현재 줄의 가장 앞으로 이동)</td>
</tr>
<tr>
<td><code>\f</code></td>
<td>폼 피드(줄 바꿈 문자, 커서를 현재 줄의 다음 줄로 이동)</td>
</tr>
<tr>
<td><code>\a</code></td>
<td>벨 소리(출력할 때 PC 스피커에서 '삑' 소리가 난다)</td>
</tr>
<tr>
<td><code>\b</code></td>
<td>백 스페이스</td>
</tr>
<tr>
<td><code>\000</code></td>
<td>널 문자</td>
</tr>
</tbody>
</table>


```python
# 문자열 길이 구하기
a = "Life is too short"
b = "Life is" + "too short"

print(len(a))
print(len(b))
print(a + str(len(a)) + "lamo")
```

    17
    16
    Life is too short17lamo



```python
# 문자열 인덱싱
a = "Life is too short, You need python"

print(a[1] + a[8])
# 인덱싱을 이용한 house 글자 만들어보기
print(a[13] + a[9] + a[21] + a[12] + a[3])
```

    it
    house



```python
# 슬라이싱, 0 <= x < 4
a = "Life is too short, You need python"
print(a[:4]) # 0 ~ 3 index
#short
print(a[12:17])
# 문장
print(a[19:]) # 19 ~ End
print(a[19:-4]) # 이 문장에서 인덱스 -4는 인덱스 30
```

    Life
    short
    You need python
    You need py



```python
a = "20230331Rainy"
year = a[:4]
day = a[4:8]
weather = a[8:]
print(year)
print(day)
print(weather)
```

    2023
    0331
    Rainy



```python
a = "Pithon"
print(a[:1] + 'y' + a[2:])
```

    Python



```python
# 심화
a = "Life is too short, You need python"
print(a[::2]) # 마지막은 step
print(a[::-1])
```

    Lf stosot o edpto
    nohtyp deen uoY ,trohs oot si efiL



```python
# 문제
today = '20260203오늘은쌀쌀하다'
# 목표값
print("2026년 2월 3일")
# 풀이
year = today[:4]
month = today[5:6]
day = today[7:8]
print(year + '년 ' + month + '월 ' + day + '일')
```

    2026년 2월 3일
    2026년 2월 3일



```python
# 테스트
import time as t
# dir(t)
```


```python
# 응용
import requests as req
url = "https://v.daum.net/v/20260203110106957"
res = req.get(url).text
print(res[:600])
print(res.find("출석"))
print(res[374:413])
```

    <!doctype html>
    <html class="os_window"> 
     <head data-cloud-area="head"> 
      <meta charset="utf-8"> 
      <meta http-equiv="X-UA-Compatible" content="IE=edge"> 
      <meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no"> 
      <meta name="format-detection" content="telephone=no"> 
      <meta name="referrer" content="unsafe-url"> 
      <title>[뉴스1 PICK]'국회 위증' 혐의, 박대준 전 쿠팡 대표 경찰 출석</title> 
      <link rel="shortcut icon" href="//t1.daumcdn.net/top/favicon/20241223/daum.ico"> 
      <meta property="mccp:docId" content="Uh72xu6bG7"> 
      <meta property="og:site_name" content=
    411
    [뉴스1 PICK]'국회 위증' 혐의, 박대준 전 쿠팡 대표 경찰 출석



```python
import requests as req

url = "https://v.daum.net/v/20260203120206039"
res = req.get(url).text
n = "오영석"
r = res.find(n)

# if r == -1:
#     print("검색 결과가 없습니다.")
# else:
#     start = 0
#     while r != -1:
#         start = r + len(n)
#         print(res[r:r+80])
#         r = res.find(n, start)
print(res[17496:17568])
```

    오영석 박사는 "앞으로 고내열 수지와 결합해 적정 온도를 500℃ 수준까지 끌어올리고, 실제 부품 환경에서 신뢰성을 검증할 계획"



```python
import requests as req

url = "https://api4.binance.com/api/v3/ticker/price?symbol=BTCUSDT"
res = req.get(url).text
r = res.find("price")
bc = res[29:34]
print("비트코인 가격(달러): $" + bc)
won = str(int(res[29:34]) * 1450) 
print("비트코인 가격(원): " + won[:1] + '억 ' + won[1:5] + '만 ' + won[5:9] + '원')
```

    비트코인 가격(달러): $78421
    비트코인 가격(원): 1억 1371만 0450원


### 문자열 포매팅


```python
# 문자열 포매팅, 대입
n = 5
print("I eat %d apples." % n)
```

    I eat 5 apples.



```python
print("I eat %s apples." % n)
```

    I eat 5 apples.



```python
inp = input("몇 개인지 입력하세요.")
print("I eat %d apples." % (int(inp)*10))
```

    몇 개인지 입력하세요. 10


    I eat 100 apples.



```python
# 2개 이상의 값 넣기
number = 10
day = 10
"I ate %d apples. so I was sick for %s days." % (number, day)
```




    'I ate 10 apples. so I was sick for 10 days.'



#### 문자열 포맷 코드

<table style="float:left">
<thead>
<tr>
<th>코드</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr>
<td>%s</td>
<td><mark>문자열(String)</mark></td>
</tr>
<tr>
<td>%c</td>
<td>문자 1개(character)</td>
</tr>
<tr>
<td>%d</td>
<td><mark>정수(Integer)</mark></td>
</tr>
<tr>
<td>%f</td>
<td><mark>부동소수(floating-point)</mark></td>
</tr>
<tr>
<td>%o</td>
<td>8진수</td>
</tr>
<tr>
<td>%x</td>
<td>16진수</td>
</tr>
<tr>
<td>%%</td>
<td>Literal % (문자 <code>%</code> 자체)</td>
</tr>
</tbody>
</table>


```python
# 문자열
print("%s" % '12.34 문자 표현')
# 정수
print("%d" % 12.34)
# 부동소수
print("%f" % 12.34)
# %% 표기
print("한국에 산은 %d%% 정도 있습니다" % 70)
```

    12.34 문자 표현
    12
    12.340000
    한국에 산은 70% 정도 있습니다



```python
# 문자열
print("%20s" % '12.34 문자 표현')
# 정수
print("%10d" % 12.34)
# 부동소수
print("%10.2f" % 12.34)
# %% 표기
print("한국에 산은 %10d%% 정도 있습니다" % 70)
```

             12.34 문자 표현
            12
         12.34
    한국에 산은         70% 정도 있습니다



```python
# 소수점 표현하기
print("%.2fkkkkk" % 3.141592)
print("%10.2fkkkkk" % 3.141592)
print("%-10.2fkkkkk" % 3.141592)
```

    3.14kkkkk
          3.14kkkkk
    3.14      kkkkk


![image.png](18086631-de98-4e0e-94f4-696e5a2272fd.png)

### format 함수를 사용한 포매팅


```python
# 숫자값을 가진 변수로 대입하기
print("I eat {0} apples".format(3)) # String에 있는 format 옵션
ss = "I eat {0} apples".format("five")
print(ss, type(ss))
```

    I eat 3 apples
    I eat five apples <class 'str'>



```python
# 2개 이상 값 넣기
s = "five"
e = 7
ss = "I ate {0} apples. so I was sick for {1} days".format(s, e)
print(ss, type(ss))
```

    I ate five apples. so I was sick for 7 days <class 'str'>



```python
# 혼용해서 넣기
sss = "I ate {number} apples. so I was sick for {day} days.".format(number=10, day=3)
print(sss)
```

    I ate 10 apples. so I was sick for 3 days.



```python
# 왼쪽 정렬
print("{0:<10}".format("hi"))
# 오른쪽 정렬
print("{0:>10}".format("hi"))
# 가운데 정렬
print("{0:^10}".format("hi"))
```

    hi        
            hi
        hi    



```python
re = "{0:.^17}".format("영수증")
print("="*20 + "\n" + re + "\n" + "="*20)
```

    ====================
    .......영수증.......
    ====================



```python
# input으로 개수를 입력받아
# 한잔에 2500원인 아아와 3800원인 라떼를 계산한 영수증을 출력하라.
i = 2500
l = 3800
n = input("아아 개수")
m = input("아아 개수")
s = "{0:.^17}".format("영수증")

print("="*20 + "\n" + s + "\n" + "-"*20)
print("{0:>9}".format("아아 ") + n + "잔")
print("{0:>9}".format("라떼 ") + m + "잔")
print("."*20)
print("{0:>7}".format("아아 ") + str(i * int(n)) + "원")
print("{0:>7}".format("라떼 ") + str(i * int(m)) + "원")
print("-"*20)
print(">>>> 총 가격: {0}원".format((i * int(n)) + i * int(m)))
```

    아아 개수 5
    아아 개수 5


    ====================
    .......영수증.......
    --------------------
          아아 5잔
          라떼 5잔
    ....................
        아아 12500원
        라떼 12500원
    --------------------
    >>>> 총 가격: 25000원



```python

```
