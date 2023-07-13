
 
# YOLOv5를 이용한 무인 점포 계산 시스템의 구현 
> 2022-1학기 빅데이터/인공지능 융합전공 캡스톤 디자인 <br>
> YOLOv5를 이용하여 바코드가 아닌 이미지 인식을 통해 계산할 수 있는 시스템 구현
<br>

## 1. 소개 
> 진행 기간: 2022. 03 ~ 2022. 06 <br>


- 기존 바코드 인식을 통해 물품을 계산하는 시스템은 이용자가 직접 바코드를 찾아 스캔해야 하는 불편함이 있다. 
- 본 논문에서는 YOLOv5를 이용하여 바코드가 아닌 이미지 인식을 통해 계산할 수 있는 시스템을 구현하였다. 
- 초기 이미지 학습은 웹 크롤링과 직접 수집한 데이터를 이용하였고, OpenCV를 이용하여 별도의 라벨링 없이 자동으로 라벨링 해줄 수 있는 물품 등록기능을 추가하였다. 
- 본 연구를 통해 개선된 시스템은 **기존 결제 시스템보다 결제 시간이 약 20% 단축**되었다.
<img width="960" alt="image" src="https://github.com/seoeunhyo/Implementation-of-calculation-system-using-YOLOv5-at-unmanned-store/assets/93567740/73c7958e-1733-44ee-a49f-10cb86d4bb0e">

<br>

## 2. 사용 기술 

#### Libraries
- `yolov5`
- `numpy`
- `OpenCV`
- `os`
  
#### Train
- `Google Colaboratory`

#### Language
- Anaconda3 기반 `Python 3.9.0`

#### Enviroment
- `Windows 10`

#### Processor
- Intel(R) Core(TM) i3-6006U 
	        CPU @ 2.00GHz, 2000Mhz, 
	        2 core, 4 논리 프로세서
-  OS name: Microsoft Windows 10 Pro
-  RAM: 12.0GB

<br>

## 3. 관련 연구
<img width="960" alt="image" src="https://github.com/seoeunhyo/Implementation-of-calculation-system-using-YOLOv5-at-unmanned-store/assets/93567740/92d0a7f1-399f-4847-81b4-0b642d4edcd7">

<br> 
<br>

## 4. 문제 해결 방법

1. 시중에서 판매하는 아이스크림 이미지를 학습데이터로 이용 
막대 모양(bar), 고깔 모양(Corn), 컵 모양(Cup) 각각 두 개씩 선정

2. 새로운 물품 등록, 물품 인식 및 계산 그리고 프로그램 종료 탭 제공


