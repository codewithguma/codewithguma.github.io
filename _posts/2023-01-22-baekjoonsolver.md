---
layout: single
title: "Baekjoon Solver Project"
categories:
  - arduino
tags:
  - 현수
  - 하람
  - 종원
  - 서빈
---

<img src="https://drive.google.com/uc?export=download&id=1Is9gw54qaOvjkTNVi1ZRsC2ljT2qrRBy" width=500>

## Arduino code

```cpp
#include <LiquidCrystal.h>

const int rs = 12, en = 11, d4 = 5, d5 = 4, d6 = 3, d7 = 2;
LiquidCrystal lcd(rs, en, d4, d5, d6, d7);
int input_data;

void setup() {
  Serial.begin(9600);
  lcd.begin(16, 2);
  lcd.print("Baekjoon Solver");
}

void loop() {
  if(Serial.available()) {
    lcd.setCursor(0, 1);
    lcd.print("                ");
    String str = "";
    while(Serial.available()) {
      char ch = Serial.read();
      str.concat(ch);
    }
    lcd.setCursor(0, 1);
    lcd.print(str);
  }
}
```

## Python code

예시로는 [1157번: 단어 공부](https://www.acmicpc.net/problem/1157) 코드를 사용했습니다!

```python
word = input().upper()
counts = {}
for letter in word:
    if letter in counts:
        counts[letter] += 1
    else:
        counts[letter] = 1
sorted_counts = sorted(counts.items(), key=lambda item: item[1], reverse=True)
if len(sorted_counts) >= 2 and sorted_counts[0][1] == sorted_counts[1][1]:
    print('?')
else:
    print(sorted_counts[0][0])
```

```python
import serial
import time

# 'COM7' 부분에 환경에 맞는 포트 입력
ser = serial.Serial('COM7', 9600)

def baekjoon_solver():
    word = input().upper()
    if word == 'END':
        return 'end'
    counts = {}
    for letter in word:
        if letter in counts:
            counts[letter] += 1
        else:
            counts[letter] = 1
    sorted_counts = sorted(counts.items(), key=lambda item: item[1], reverse=True)
    if len(sorted_counts) >= 2 and sorted_counts[0][1] == sorted_counts[1][1]:
        return '?'
    else:
        return sorted_counts[0][0]

while True:
    if ser.readable():
        val = baekjoon_solver()

        if val == 'end':
            ser.close()
            print('Bye😭')
            break

        else:
            val_ = val.encode('utf-8')
            ser.write(val_)
            print(f"👍 '{val}' printed!")
            time.sleep(0.5)
```

    hello
    👍 'L' printed!
    mississipi
    👍 '?' printed!
    happy
    👍 'P' printed!
    end
    Bye😭

## Results

![arduino](https://github.com/codewithguma/codewithguma.github.io/raw/master/_posts/arduino.gif)
