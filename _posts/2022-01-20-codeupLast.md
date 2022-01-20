---
layout: single
title:  "codeup 기초 100제 6091~6095번"
categories: python
---

##### 코드업 기초 100제 기초리스트 볼 부분

----

**이상한 출석번호 부르기1**

```python
n = int(input()) # 몇 번 부를 지 저장
a = input().split() # 출석번호를 불러 a 리스트에 저장한다.

# a 리스트에 저장된 수를 정수형으로 바꾼다.
for i in range(n): 
    a[i] = int(a[i])
    
d=[] # 각 변호 별로 몇 번 불렸는 지 저장할 리스트 
for i in range(24):
    d.append(0) # 0으로 초기화.

# 불린 번호에 카운트를 1씩 증가시킨다.
for i in range(n):
    d[a[i]] += 1 

for i in range(1, 24):# 1~23번까지 출력하기
    print(d[i], end=' ')
```

**이상한 출석번호 부르기2**

```python
n = int(input()) # 몇 번 부를 지 저장
a = input().split() # 출석번호를 불러 a 리스트에 저장한다.

# a 리스트에 저장된 수를 정수형으로 바꾼다.
for i in range(n): 
    a[i] = int(a[i])

for i in range(n-1, -1, -1):
    print(a[i], end=' ')
```

range(시작, 끝, 증감) 시작 수는 포함, 끝 수는 포함하지 않음. [시작, 끝)
range(n-1, -1, -1) n-1, n-2, ..., 3, 2, 1, 0

n-1이 리스트의 마지막 요소를 의미한다.

**이상한 출석번호 부르기3**

내 풀이:

```python
n = int(input()) # 몇 번 부를 지 저장
a = input().split() # 출석번호를 불러 a 리스트에 저장한다.

for i in range(n): # 정수형으로 요소 값을 저장한다.
    a[i] = int(a[i])
print(min(a)) # 가장 빠른 번호를 출력한다: 가장 작은 요솟값을 출력한다.
```

min함수는 리스트 내에 있는 최솟값을 돌려준다.

----

사이트 풀이: 

```python
n = int(input())
a = input().split()

for i in range(n) :
  a[i] = int(a[i])

min = a[0] # 최솟값을 첫 인덱스로 저장
for i in range(0, n) : 
  if a[i] < min : # 더 작은 값이 있으면
    min = a[i] # 최솟값을 바꾼다.
print(min)
```

----

----

**바둑판에 흰 돌 놓기**

```python
d=[] 
for i in range(20) :
  d.append([])         #리스트 안에 다른 리스트 추가해 넣기
  for j in range(20) : 
    d[i].append(0)    #리스트 안에 들어있는 리스트 안에 0 추가해 넣기

n = int(input()) # 몇 번 돌을 놓을 건지
for i in range(n) : # 바둑돌이 올려진 자리는 1로 비뀐다.
  x, y = map(int, input().split())
  d[x][y] = 1

for i in range(1, 20) : 
  for j in range(1, 20) : 
    print(d[i][j], end=' ')    #공백을 두고 한 줄로 출력
  print()                          #줄 바꿈
```

2차원 배열 간단하게 만들기:

```python
d=[[0]*20 for i in range(20)]

n = int(input()) # 몇 번 돌을 놓을 건지
for i in range(n) : # 바둑돌이 올려진 자리는 1로 비뀐다.
  x, y = map(int, input().split())
  d[x][y] = 1

for i in range(1, 20) : 
  for j in range(1, 20) : 
    print(d[i][j], end=' ')    #공백을 두고 한 줄로 출력
  print()                          #줄 바꿈
```

배열은 20*20으로 만든다. 사용자에게 입력받을 떄도 1,1을 입력받으면 그대로 d[1] [1] =1로 대입한다. 다만, 출력할 때는 두번째 인덱스부터 출력한다. 즉, 출력할 때 range(1, 20)을 사용하여 1~19까지 출력한다. d 배열은 0~19인덱스까지 있지만, 인덱스 0을 제외하여 출력한다. 만약 0번째 인덱스를 이런식으로 남겨놓지 않으려면

```python
d=[[0]*19 for i in range(19)]

n = int(input()) # 몇 번 돌을 놓을 건지
for i in range(n) : # 바둑돌이 올려진 자리는 1로 비뀐다.
  x, y = map(int, input().split())
  d[x-1][y-1] = 1

for i in range(19) : 
  for j in range(19) : 
    print(d[i][j], end=' ')    #공백을 두고 한 줄로 출력
  print()                          #줄 바꿈
```

이렇게 작성할 수도 있다.

