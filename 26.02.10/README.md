# 제어문

## if 문 **


```python
if True:
    print("조건문 실행")
```

    조건문 실행



```python
# if 구문

money = "돈있어"

if money == "돈있어":
    print("택시타고가")
else:
    print("걸어가")
```

    택시타고가


<table style="float:left">
<thead>
<tr>
<th>비교연산자</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr>
<td>x &lt; y</td>
<td>x가 y보다 작다.</td>
</tr>
<tr>
<td>x &gt; y</td>
<td>x가 y보다 크다.</td>
</tr>
<tr>
<td>x == y</td>
<td>x와 y가 같다.</td>
</tr>
<tr>
<td>x != y</td>
<td>x와 y가 같지 않다.</td>
</tr>
<tr>
<td>x &gt;= y</td>
<td>x가 y보다 크거나 같다.</td>
</tr>
<tr>
<td>x &lt;= y</td>
<td>x가 y보다 작거나 같다.</td>
</tr>
</tbody>
</table>


```python
if money != "돈없어":
    print("과자 사먹자")
```

    과자 사먹자


### in, not in
<table style="float:left">
<thead>
<tr>
<th>in</th>
<th>not in</th>
</tr>
</thead>
<tbody>
<tr>
<td>x in 리스트</td>
<td>x not in 리스트</td>
</tr>
<tr>
<td>x in 튜플</td>
<td>x not in 튜플</td>
</tr>
<tr>
<td>x in 문자열</td>
<td>x not in 문자열</td>
</tr>
</tbody>
</table>


```python
print(1 in [1, 2, 3])
print(1 not in [1, 2, 3])
print('j' not in "python")
```

    True
    False
    True



```python
pocket = ['paper', 'key', 'money']
if money in pocket:
    print("택시를 타고가라")
else:
    print("걸어가라")
```

    걸어가라



```python
pocket = ['paper', 'key', 'money']
if 'money' in pocket:
    pass
else:
    print("걸어가라")
```


```python
# 조건부 표현식1
age = 19
status = "성인" if age >= 18 else "미성년"
print(status)

# 조건부 표현식2
temperature = 25
weather = "따뜻함" if temperature > 20 else "추움"
print(weather)

# 조건부 표현식3
money = 1500
transportation = "버스" if money >= 1000 else "도보"
print(transportation)
```

    성인
    따뜻함
    버스



```python
# if elif
pocket = ['paper', 'key']
card = True
if 'money' in pocket:
    print("돈으로 택시 타라")
elif card == True:
    print("카드로 택시 타라")
else:
    print("걸어가라")
```

    카드로 택시 타라



```python
# if만 사용
pocket = ['paper', 'key']
card = True
if 'money' in pocket:
    print("돈으로 택시 타라")
if card != True:
    print("카드로 택시 타라")
if not 'money' in pocket and not card == True:
    print("걸어가라")
```

### 문제 및 실습


```python
# 문제
# 만약 5000원 이상의 돈을 가지고 있으면 택시를 타고가고, 그렇지 않으면 걸어가라

money = input("얼마가 있나요?")

if int(money) >= 5000:
    print("택시를 타고가라")
else:
    print("걸어가라")
```

    얼마가 있나요? 5000


    택시를 타고가라



```python
# 문제2
identify = True # "있다"
stamp = True # "있다"
sign = True # "할수있다"

print("어서오세요.")
inp1 = "있다" in input("신분증이 있나요?")
inp2 = "있다" in input("도장이 있나요?")
inp3 = "있다" in input("싸인할 수 있나요?")
inp4 = "한국" in input("국적이 어딘가요?")

if (inp1 and (inp2 or inp3)) and not inp4:
    print("업무 진행 가능합니다.")
else:
    print("서류가 부족합니다.")
```

    어서오세요.


    신분증이 있나요? 있음
    도장이 있나요? 있음
    싸인할 수 있나요? 없음
    국적이 어딘가요? 미국


    서류가 부족합니다.



```python
# 문제3
dic = {"name": "hong", "age": 23, "gender": "male"}

# 나이가 20살 이상이며 성별이 male이면 군대가기
if dic["age"] >= 20 and dic["gender"] == "male":
    print("군대가기")
else:
    pass
```

    군대가기



```python
# 조건부 표현식
# 조건부 표현식에서는 pass문을 쓸 수 없음
print("군대가기" if dic["age"] >= 20 and dic["gender"] == "male" else "")
```

    군대가기



```python
# 응용1 (if elif)
score = 80
```

## while 문 **


```python
check = 0
while check < 10:
    check += 1
    print("가자", check)
    
check = 0
while check < 10:
    print("가자", check)
    check += 1
```

    가자 1
    가자 2
    가자 3
    가자 4
    가자 5
    가자 6
    가자 7
    가자 8
    가자 9
    가자 10
    가자 0
    가자 1
    가자 2
    가자 3
    가자 4
    가자 5
    가자 6
    가자 7
    가자 8
    가자 9



```python
coffee = 5
money = 300
while money:
    print("돈을 받았으니 커피를 줍니다.")
    coffee = coffee -1
    print("남은 커피의 양은 %d개입니다." % coffee)
    if coffee == 0:
        print("커피가 다 떨어졌습니다. 판매를 중지합니다.")
        break
```

    돈을 받았으니 커피를 줍니다.
    남은 커피의 양은 4개입니다.
    돈을 받았으니 커피를 줍니다.
    남은 커피의 양은 3개입니다.
    돈을 받았으니 커피를 줍니다.
    남은 커피의 양은 2개입니다.
    돈을 받았으니 커피를 줍니다.
    남은 커피의 양은 1개입니다.
    돈을 받았으니 커피를 줍니다.
    남은 커피의 양은 0개입니다.
    커피가 다 떨어졌습니다. 판매를 중지합니다.



```python
# random으로 스토리 생성기 만들기

characters = [""]
```


```python
# 응용
import random as ran

li = []
i = 0
cc = int(input("몇 회 주사위를 던질까요?") or 100)
while i < cc:
    num = ran.randint(1, 6)
    li.append(num)
    i += 1

if cc == len(li):
    print(f"{cc} 회 정상 진행 되었습니다.")
    print("1번이 %d번 등장 %.2f%%" % (li.count(1), ((li.count(1)/i)*100)))
    print("2번이 %d번 등장 %.2f%%" % (li.count(2), ((li.count(2)/i)*100)))
    print("3번이 %d번 등장 %.2f%%" % (li.count(3), ((li.count(3)/i)*100)))
    print("4번이 %d번 등장 %.2f%%" % (li.count(4), ((li.count(4)/i)*100)))
    print("5번이 %d번 등장 %.2f%%" % (li.count(5), ((li.count(5)/i)*100)))
    print("6번이 %d번 등장 %.2f%%" % (li.count(6), ((li.count(6)/i)*100)))
else:
    print(f"검증 결과 이상이 있습니다. {cc}회 목표로 동작하였으나, {len(li)}으로 측정되었습니다.")
```

    몇 회 주사위를 던질까요? 1000


    1000 회 정상 진행 되었습니다.
    1번이 162번 등장 16.20%
    2번이 174번 등장 17.40%
    3번이 156번 등장 15.60%
    4번이 183번 등장 18.30%
    5번이 171번 등장 17.10%
    6번이 154번 등장 15.40%



```python
# 로또 번호
# 1 ~ 45 임의의 수 중에서 중복없는 6개의 수를 뽑아 나열하여 분석하시오.
import random as ran

li = []

while len(li) < 6:
    num = ran.randint(1, 45)
    if num not in li:
        li.append(num)
        
li.sort()
print(li)
```

    [9, 13, 18, 24, 33, 37]


## for 문 **


```python
# 리스트 순회
list_1 = ["orange", "banana", "kiwi", "melon"]

for i in list_1:
    print(i)
```

    orange
    banana
    kiwi
    melon



```python
st = "안녕하세요"
for s in st:
    print(s)
```

    안
    녕
    하
    세
    요



```python
arr = [(1,2), (3,4), (5,6)]
# a, b = 1, 2
for (a, b) in arr:
    print(a + b)
```

    3
    7
    11



```python
marks = [90, 25, 67, 45, 80, 77]
num = 0
for m in marks:
    num += 1
    if m >= 60:
        print("{0}번 학생은 {1}점으로 합격입니다.".format(num, m))
    else:
        print("{0}번 학생은 {1}점으로 불합격입니다.".format(num, m))
```

    1번 학생은 90점으로 합격입니다.
    2번 학생은 25점으로 불합격입니다.
    3번 학생은 67점으로 합격입니다.
    4번 학생은 45점으로 불합격입니다.
    5번 학생은 80점으로 합격입니다.
    6번 학생은 77점으로 합격입니다.



```python
marks = [90, 25, 67, 45, 80, 77]
num = 0
for m in marks:
    num += 1
    if m < 60:
        continue
    print("%d번 학생은 %d점으로 합격입니다." % (num, m))
```

    1번 학생은 90점으로 합격입니다.
    3번 학생은 67점으로 합격입니다.
    5번 학생은 80점으로 합격입니다.
    6번 학생은 77점으로 합격입니다.



```python
# range
marks = [90, 25, 67, 45, 80, 77]

for i in range(0, 6, 1):
    print(marks[i])
```

    90
    25
    67
    45
    80
    77



```python
li = []
li2 = []
li3 = []
num = 0

for i in range(3, 12):
    li.append(i)
    
for i in range(1, 14, 3):
    li2.append(i)
    
for i in range(0, 51, 2):
    li3.append(i)

for i in range(1, 11):
    num += i
    
print(li)
print(li2)
print(li3)
print(num)
```

    [3, 4, 5, 6, 7, 8, 9, 10, 11]
    [1, 4, 7, 10, 13]
    [0, 2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30, 32, 34, 36, 38, 40, 42, 44, 46, 48, 50]
    55



```python
marks = [90, 25, 67, 45, 80, 77]
number = 0
for number in range(len(marks)):
    if marks[number] < 60:
        continue
    print("%d번 학생은 %d점으로 합격입니다." % (number, marks[number]))
```

    0번 학생은 90점으로 합격입니다.
    2번 학생은 67점으로 합격입니다.
    4번 학생은 80점으로 합격입니다.
    5번 학생은 77점으로 합격입니다.



```python
# 구구단 문제
i = 0
j = 0
for i in range(2, 10):
    print("="*10 + "\n" + f"{i:>5}단" + "\n" + "-"*10)
    for j in range(1, 10):
        print(f"{i} x {j} = {i*j}")
```

    ==========
        2단
    ----------
    2 x 1 = 2
    2 x 2 = 4
    2 x 3 = 6
    2 x 4 = 8
    2 x 5 = 10
    2 x 6 = 12
    2 x 7 = 14
    2 x 8 = 16
    2 x 9 = 18
    ==========
        3단
    ----------
    3 x 1 = 3
    3 x 2 = 6
    3 x 3 = 9
    3 x 4 = 12
    3 x 5 = 15
    3 x 6 = 18
    3 x 7 = 21
    3 x 8 = 24
    3 x 9 = 27
    ==========
        4단
    ----------
    4 x 1 = 4
    4 x 2 = 8
    4 x 3 = 12
    4 x 4 = 16
    4 x 5 = 20
    4 x 6 = 24
    4 x 7 = 28
    4 x 8 = 32
    4 x 9 = 36
    ==========
        5단
    ----------
    5 x 1 = 5
    5 x 2 = 10
    5 x 3 = 15
    5 x 4 = 20
    5 x 5 = 25
    5 x 6 = 30
    5 x 7 = 35
    5 x 8 = 40
    5 x 9 = 45
    ==========
        6단
    ----------
    6 x 1 = 6
    6 x 2 = 12
    6 x 3 = 18
    6 x 4 = 24
    6 x 5 = 30
    6 x 6 = 36
    6 x 7 = 42
    6 x 8 = 48
    6 x 9 = 54
    ==========
        7단
    ----------
    7 x 1 = 7
    7 x 2 = 14
    7 x 3 = 21
    7 x 4 = 28
    7 x 5 = 35
    7 x 6 = 42
    7 x 7 = 49
    7 x 8 = 56
    7 x 9 = 63
    ==========
        8단
    ----------
    8 x 1 = 8
    8 x 2 = 16
    8 x 3 = 24
    8 x 4 = 32
    8 x 5 = 40
    8 x 6 = 48
    8 x 7 = 56
    8 x 8 = 64
    8 x 9 = 72
    ==========
        9단
    ----------
    9 x 1 = 9
    9 x 2 = 18
    9 x 3 = 27
    9 x 4 = 36
    9 x 5 = 45
    9 x 6 = 54
    9 x 7 = 63
    9 x 8 = 72
    9 x 9 = 81


### 리스트 컴프리헨션 사용하기


```python
a = [1, 2, 3, 4]
b = []
for x in a:
    b.append(x**2)
print(b)
```

    [1, 4, 9, 16]



```python
b = [x**2 for x in a]
print(b)
```

    [1, 4, 9, 16]



```python
c = [x+5 for x in a]
print(c)
```

    [6, 7, 8, 9]



```python
a = [r for r in range(0,101)]
b = [r for r in range(0,101) if r % 2 == 0]
c = [r for r in range(0,101) if r % 2 == 1] 
print(c)
```

    [1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21, 23, 25, 27, 29, 31, 33, 35, 37, 39, 41, 43, 45, 47, 49, 51, 53, 55, 57, 59, 61, 63, 65, 67, 69, 71, 73, 75, 77, 79, 81, 83, 85, 87, 89, 91, 93, 95, 97, 99]



```python
# 구구단을 리스트 컴프리헨션 사용하기
a = [i*j for i in range(2,10) for j in range(1,10)]
print(a)
```

    [2, 4, 6, 8, 10, 12, 14, 16, 18, 3, 6, 9, 12, 15, 18, 21, 24, 27, 4, 8, 12, 16, 20, 24, 28, 32, 36, 5, 10, 15, 20, 25, 30, 35, 40, 45, 6, 12, 18, 24, 30, 36, 42, 48, 54, 7, 14, 21, 28, 35, 42, 49, 56, 63, 8, 16, 24, 32, 40, 48, 56, 64, 72, 9, 18, 27, 36, 45, 54, 63, 72, 81]


### enumerate 함수 활용하기


```python
arr = [11,22,33,44,55]
for i, a in enumerate(arr, 3):
    print(i,a) # i는 인덱스, a는 값
```

    3 11
    4 22
    5 33
    6 44
    7 55


### zip 함수로 여러 리스트 함께 순회하기


```python
names = ['홍길동', '김철수', '이영희', '이순신']
scores = [85, 92, 78, 99]
grade = ["합격" if x > 80 else "불합격" for x in scores]

for x, y, z in zip(names, scores, grade):
    print(f"{x}님은 {y}점 이므로 {z}입니다.")
```

    홍길동님은 85점 이므로 합격입니다.
    김철수님은 92점 이므로 합격입니다.
    이영희님은 78점 이므로 불합격입니다.
    이순신님은 99점 이므로 합격입니다.



```python
# 테스트 타이머
import time as tt
for x in range(11):
    print(f"{('■')*x:□<10} {x*10}%", end="\r")
    tt.sleep(1)
```

    ■■■■■■■■■■ 100%


```python
# !pip install tqdm
```

    Requirement already satisfied: tqdm in ./venv/lib/python3.12/site-packages (4.67.3)



```python
# tqdm 프로그래스 시각화
from tqdm import tqdm
import time as tt
for x in tqdm(range(100)):
    pass
    tt.sleep(0.1)
```

    100%|█████████████████████████████████████████████████████████████████████| 100/100 [00:10<00:00,  9.77it/s]



```python
import time as tt
arr = []
length = 100*1000*1000
for x in range(length):
    arr.append(x)
arr_T = tuple(arr)
print(type(arr))
print(type(arr_T))
```

    <class 'list'>
    <class 'tuple'>



```python
# 리스트 순회 시간
start = tt.time()
for a in arr:
    lts = [1, 2, 3, 4, 5] # 순회 과정 중 리스트를 읽어들일 때 느려짐
else:
    print(tt.time() - start)
```

    3.8488616943359375



```python
# 튜플 순회 시간
start2 = tt.time()
for a in arr_T:
    lts = (1, 2, 3, 4, 5)
else:
    print(tt.time() - start2)
```

    1.986541509628296

