```python
# 비트코인 API
import requests as req
url = "https://api.bithumb.com/v1/candles/minutes/1?market=KRW-BTC&count=1"
d_url = "https://api.bithumb.com/v1/candles/days?market=KRW-BTC&count=1"
ori = req.get(url).json()[0]
ori2 = req.get(d_url).json()[0]

# '''분봉'''
# 시작가
openp = float(ori['opening_price'])
# 최고가
maxp = float(ori['high_price'])
# 최저가
minp = float(ori['low_price'])
# 변화폭
bandp = maxp - minp

# '''일봉'''
# 시작가
openp2 = float(ori2['opening_price'])
# 최고가
maxp2 = float(ori2['high_price'])
# 최저가
minp2 = float(ori2['low_price'])
# 변화폭
bandp2 = maxp2 - minp2

print("분기준\n시작가:", openp, "\n최고가:", maxp, "\n최저가:", minp, "\n변화폭:", bandp)

f = maxp < (openp + bandp)
print("최종:", "상승장\n" if f > 0 else "하락장\n")

print("일기준\n시작가:", openp2, "\n최고가:", maxp2, "\n최저가:", minp2, "\n변화폭:", bandp2)

f2 = maxp2 < (openp2 + bandp2)
print("최종:", "상승장\n" if f > 0 else "하락장\n")

# print("검토:", openp + bandp)
# print("최고가:", maxp)
```

    분기준
    시작가: 98144000.0 
    최고가: 98225000.0 
    최저가: 97989000.0 
    변화폭: 236000.0
    최종: 상승장
    
    일기준
    시작가: 101900000.0 
    최고가: 102129000.0 
    최저가: 88999000.0 
    변화폭: 13130000.0
    최종: 상승장
    



```python
# 판단하기

# 개인스킬
me = 'c'
# 모집공고 요구스킬
compA = ['JAVA', 'PYTHON', 'HTML', 'Javascript', 'C', 'ORACLE']
compB = ['HTML', 'PyThon', 'C', 'MySQL']
compC = ['JAVA', 'HTML', 'CSS', 'Javascript', 'C++', 'ORACLE']

print("합격 여부")
print("compA:", "합격" if str(me).lower() in str(compA).lower() else "불합격")
print("compB:", "합격" if str(me).lower() in str(compB).lower() else "불합격")
print("compC:", "합격" if str(me).lower() in str(compC).lower() else "불합격")
```

    합격 여부
    compA: 합격
    compB: 합격
    compC: 합격



```python
# 정제하기 (국제우주정거장 실시간 위치)

import requests as req
import webbrowser as wb

# 위성 위치
url = "http://api.open-notify.org/iss-now.json"
# 탑승자 명단
url2 = "http://api.open-notify.org/astros.json"

result = req.get(url).json()
lat = result['iss_position']['latitude']
lon = result['iss_position']['longitude']

human_num = req.get(url2).json()['number']

url3 = f"http://www.google.com/maps?q={lat},{lon}"
print(f"현재 {human_num}명이 탑승한 인공위성(국제우주정거장) 위치를 열겠습니다. 위도:{lat}, 경도:{lon}")
wb.open(url3)
```

    현재 12명이 탑승한 인공위성(국제우주정거장) 위치를 열겠습니다. 위도:-15.7470, 경도:-19.9343





    True



    gio: http://www.google.com/maps?q=-15.7470,-19.9343: Operation not supported



```python
# 지역 날씨

import requests as req

url = "https://api.open-meteo.com/v1/forecast?latitude=35.1317&longitude=129.1064&current_weather=true"
u = req.get(url).json()

lat = u['latitude']
lon = u['longitude']
tem = u['current_weather']['temperature']
win_h = u['current_weather']['windspeed']
win_d = u['current_weather']['winddirection']

print("위도:", lat)
print("경도:", lon)
print("온도:", tem, u['current_weather_units']['temperature'])
print("풍속:", win_h, u['current_weather_units']['windspeed'])
print("풍향:", win_d, u['current_weather_units']['winddirection'])

# print(u, type(u))
```

    위도: 35.15
    경도: 129.125
    온도: 7.1 °C
    풍속: 12.0 km/h
    풍향: 316 °



```python

```
