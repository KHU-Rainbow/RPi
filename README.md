# Rainbow - Raspberry Pi + Sensor

## Project Explanation
### 1. 초음파 센서
- 사용자 다리와 떨어져있는 거리 측정
- 책상 밑에 사용자의 무릎 높이에 설치
- 임계값 = 25cm 라고 설정 (RPi.c의 fDistance 값)
- 임계값을 통해 사용자가 앉은 상태 인식
### 2. FND 센서
- 누적된 공부 시간 시각화 기능 제공
- 사용자가 확인할 수 있도록 책상 위에 설치
- 자동으로 시간이 측정되는 '스탑워치' 기능 제공
- 측정 거리 < 임계값 → FND 시작
- 측정 거리 >= 임계값 → FND 멈춤
### 3. Buzzer 센서
- 시간의 누적 여부를 알려주는 청각적 알림 센서
- 측정 거리 < 임계값 → Buzzer 도미솔♬
- 측정 거리 >= 임계값 → Buzzer 솔미도♬

## Build Method
- **Basic Configuration**
```
sudo apt-get update
sudo apt-get upgrade
```
- **Install Git on RPi**
```
sudo apt-get install git
```
- **Install wiringPi on RPi**
```
+ wiringPi
- I2C, SPI, UART 등의 통신 제어 함수 제공
- GPIO 포트에 대한 설정 및 프로그래밍 인터페이스 제공

git clone https://github.com/WiringPi/WiringPi
mv WiringPi wiringPi
cd wiringPi
./build

# 잘 설치됐는지 확인
gpio -v
```
- **Compile RPi.c**
```
gcc -o RPi.c RPi -lwringPi
```