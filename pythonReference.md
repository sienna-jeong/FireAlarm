#### 구구단 만들기
```python
i = 1
j = 1
multiple = 0
while i < 10:
    while j < 10:
        multiple = i * j
        print (f'{i} * {j} = {multiple}') ##
        j += 1 
    i += 1 
    j = 1 
```

#### 1000 BREAK POINT
```python
APARTMENT_PRICE_2016 = 1_100_000_000
bank_balance = 50_000_000
```

### 복리 계산
```python
# constants
INTEREST_RATE = 0.12
FLAT_PRICE_2016 = 1100000000

# variables
year = 1988
bank_balance = 50000000  


while year < 2016 :
    bank_balance = bank_balance * (1 + INTEREST_RATE) 
    year += 1 
    
if bank_balance > FLAT_PRICE_2016:
    price_gap = bank_balance - FLAT_PRICE_2016
    print(f'{int(price_gap)}원 차이로 동일 아저씨 말씀이 맞습니다.')
else:
    price_gap = FLAT_PRICE_2016 - bank_balance
    print(f'{int(price_gap)}원 차이로 미안 아주머니 말씀이 맞습니다.')
```

#### 파보나치 수열
```python
# 힌트 4에서 이야기한 문제점은 기존 previous의 값을 잃어버린다는 것인데요.
# 이 문제를 해결하기 위해서 임시 보관소 역할을 할 변수를 만들면 됩니다.


temp = previous  # previous를 임시 보관소 temp에 저장
previous = current
current = current + temp  # temp에는 기존 previous 값이 저장돼 있음
```

### Fahrenheit to Celsius
```python
# 화씨 온도에서 섭씨 온도로 바꿔 주는 함수
def fahrenheit_to_celsius(fahrenheit):
    return (fahrenheit - 32) * 5 / 9


temperature_list = [40, 15, 32, 64, -4, 11]
print("화씨 온도 리스트: {}".format(temperature_list))  # 화씨 온도 출력

# 리스트의 값들을 화씨에서 섭씨로 변환하는 코드
i = 0
while i < len(temperature_list):
    temperature_list[i] = round(fahrenheit_to_celsius(temperature_list[i]), 1)
    i += 1

print("섭씨 온도 리스트: {}".format(temperature_list))  # 섭씨 온도 출력
```

#### Sort vs Sorted
```python
numbers = [5, 3, 1, 4, 2]  # 예시 리스트

# sorted() 함수로 정렬된 새로운 리스트를 반환받아 출력
sorted_numbers = sorted(numbers)
print("정렬된 리스트 (sorted 함수 사용):", sorted_numbers)
print("원본 리스트:", numbers)  # 원본 리스트는 변하지 않음
```

### 리스트에서 값의 존재 찾기
```python
primes = [2, 3, 5, 7, 11, 13, 17, 19, 23]
print(7 in primes)
print(12 in primes)
```

#### 사전 만들기
```python
# 일단 new_dict = {} 라고 한 것은, 텅빈 딕셔너리를 하나 미리 준비해 준 것입니다.
#; 여기에 요소를 추가하려면 new_dict['아빠'] = '최병권' 하면 '아빠': '최병권' 이라는 요소가 new_dict에 추가 되는 거죠.
# (이것을 이해해야 되요.) ; 그래서 new_dict[value] = key 가 여러번 반복되다보면, 계속해서 value값(영단어): key값(한글단어)의
# 요소들이 추가되어서 사전이 완성되는 것입니다. 그러니 저절로 영-한 사전이 됩니다.

def reverse_dict(old_dict):
    new_dict = {}  # 새로운 사전
    for key, value in old_dict.items():
        new_dict[value] = key
    return new_dict  # 변환한 새로운 사전 리턴
```

#### 단어장 만들기
```python
with open('vocabulary.txt', 'w') as f:
    while True: # 무한 루프
        # 영어 단어 입력 받기
        word = input('영어 단어를 입력하세요 (종료하려면 q): ')

        # 'q'가 입력되면 반복문 종료
        if word == 'q':
            print('Programme ended!')
            break

        # 한국어 뜻 입력 받기
        definition = input('한국어 뜻을 입력하세요: ')

        # 입력 받은 단어와 뜻을 파일에 기록
        f.write(f'{word}: {definition}\n')
```

#### Lottery winning
```python
from random import randint
import random

def generate_numbers(n):
    return random.sample(range(1, 46), n)


def draw_winning_numbers():
    winning_numbers = generate_numbers(7)
    return sorted(winning_numbers[:6]) + winning_numbers[6:]


# 테스트 코드
print(draw_winning_numbers())

# 맞춘 개수 비교
def count_matching_numbers(numbers, winning_numbers):
    count = 0

    for num in numbers:
        if num in winning_numbers:
            count = count + 1

    return count

### 상금 확인
def check(numbers, winning_numbers):
    count = count_matching_numbers(numbers, winning_numbers[:6])
    bonus_count = count_matching_numbers(numbers, winning_numbers[6:])

    if count == 6:
        return 1000000000
    elif count == 5 and bonus_count == 1:
        return 50000000
    elif count == 5:
        return 1000000
    elif count == 4:
        return 50000
    elif count == 3:
        return 5000
    else:
        return 0

```

#### 야구게임
