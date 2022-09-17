# Project name - Lazy man's musicbox

### Project idea from mitxela
https://www.youtube.com/watch?v=EuggcDJOED8

전체적인 아이디어와 디자인을 활용하였고

입력장치와 작동방식 변화를 위해 사용되는 하드웨어를 바꾸고 다른 언어로 코딩하였다.

## Project overview - 1

<img width="225" alt="사진" src="https://user-images.githubusercontent.com/34888425/190859368-b197c90e-67de-4384-a5b9-575cf8e9b9fc.png">

시중에 판매하는 punch hole music box 제품의 자동화

punch hole music box란? 

기존에 원통에 정해진대로 재생되는 오르골과 달리 종이에 구멍을 뚫어 오르골을 통과시키며 구멍의 위치에 따라 정해진 노트가 재생되는 오르골

유튜브 예시영상 : https://www.youtube.com/watch?v=8F3ijtrZ5x8

![개요1](https://user-images.githubusercontent.com/34888425/190858184-fc975c8b-6e0c-439f-b7df-a1282c458dcd.png)
이 장치는 종이에 뚫려있는 구멍을 통해 이빨이 나있는 원판을 돌리며 원판에 돋아있는 이빨을 통해 오르골의 진동판을 작동시켜 소리나게 한다.

종이에 구멍을 하나하나 뚫어주는 작동법 대신 작은 막대를 각 음의 위치마다 달아주어 서보모터로 원하는 타이밍에 밀어준다면, 악기의 자동화가 가능하다.
![개요](https://user-images.githubusercontent.com/34888425/190858351-78e8748c-8f19-4f07-8120-b789899778ab.png)

각 장치는 총 30개의 음을 소리낼 수 있으며 30개의 서보모터가 필요하다.


## Project overview - 2

![배선도](https://user-images.githubusercontent.com/34888425/190851203-b19493a3-a829-4350-b5d8-0301f60a0250.png)

Raspberry Pi 4B 하나와 아두이노등의 서보모터 컨트롤러 두가지를 사용한다.

총 31개의 모터를 운용해야하기 때문에 Raspberry Pi이외의 모터를 운용할 추가보드가 필요하다.

Raspberry Pi 의 주 기능은 두가지이다.

첫째 마스터키보드, 전자피아노등의 USB MIDI 외부디바이스와 직접 연결되어 입력되는 MIDI신호를 가공하여 서보모터 컨트롤러에 UART 통신으로 전달한다.

둘째 USB등의 메모리에서 MIDI파일 형식으로 저장되어있는 음악 파일을 열어서 해석하여 적절히 서보모터 컨트롤러에 정보를 전달한다.

![배선도2](https://user-images.githubusercontent.com/34888425/190859043-d3a2ef98-0eb4-4f95-8d4e-e7046569a5f0.png)

서보모터 컨트롤을 하는 아두이노의 기능은 한가지이다.

Raspberry Pi에서 전달하는 정보를 받아와 해당하는 서보모터를 작동시켜 오르골이 소리가 나도록 한다.

사용보드는 STM32보드 혹은 아두이노 Mega제품을 사용할 예정이다.

## Project language

Raspberry Pi - Python

Servo Controller - C
