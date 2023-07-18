

# YOLOv5를 이용한 무인 점포 계산 시스템의 구현 
> 2022-1학기 빅데이터/인공지능 융합전공 캡스톤 디자인 <br>
> YOLOv5를 이용하여 바코드가 아닌 이미지 인식을 통해 계산할 수 있는 시스템 구현 <br>
> 🌟2022 교내 캡스톤 디자인 경진대회 장려상 수상🌟
<br>

## 1. 소개 
> 진행 기간: 2022. 03 ~ 2022. 06 <br>


![image8](https://github.com/seoeunhyo/Implementation-of-calculation-system-using-YOLOv5-at-unmanned-store/assets/93567740/5cd8c925-d8bd-4178-904b-86485405f936) ![image12](https://github.com/seoeunhyo/Implementation-of-calculation-system-using-YOLOv5-at-unmanned-store/assets/93567740/df8e37e6-ab02-4a35-a187-29e766376e89)

- 기존 바코드 인식을 통해 물품을 계산하는 시스템은 이용자가 직접 바코드를 찾아 스캔해야 하는 불편함이 있다. 
- 본 논문에서는 YOLOv5를 이용하여 바코드가 아닌 이미지 인식을 통해 계산할 수 있는 시스템을 구현하였다. 
- 초기 이미지 학습은 웹 크롤링과 직접 수집한 데이터를 이용하였고, OpenCV를 이용하여 별도의 라벨링 없이 자동으로 라벨링 해줄 수 있는 물품 등록기능을 추가하였다. 
- 본 연구를 통해 개선된 시스템은 **기존 결제 시스템보다 결제 시간이 약 20% 단축**되었다.
<img width="960" alt="image" src="https://github.com/seoeunhyo/Implementation-of-calculation-system-using-YOLOv5-at-unmanned-store/assets/93567740/73c7958e-1733-44ee-a49f-10cb86d4bb0e">

<br>

## 2. 사용 기술 

#### Libraries
- `yolov5s`
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

**바코드를 인식 할 필요 없고, 데이터를 추가하는 과정이 자동화 된 무인 셀프 계산대를 고안**

1. 시중에서 판매하는 아이스크림 이미지를 학습데이터로 이용 <br>
   *(본 연구의 경우 인식하는 물품의 예를 아이스크림으로 함)*  <br>
막대 모양(bar), 고깔 모양(Corn), 컵 모양(Cup) 각각 두 개씩 선정

3. 새로운 물품 등록, 물품 인식 및 계산 그리고 프로그램 종료 기능 제공
<br>


### 4.1 새로운 물품 추가의 경우 
<br> 
<img width="960" alt="image" src="https://github.com/seoeunhyo/Implementation-of-calculation-system-using-YOLOv5-at-unmanned-store/assets/93567740/608640eb-fdfb-4736-bbe2-db14c65162ed">

### 4.2 물품 계산의 경우 
<br>

![image](https://github.com/seoeunhyo/Implementation-of-calculation-system-using-YOLOv5-at-unmanned-store/assets/93567740/4cc29039-c79e-4156-b5e2-ed835bae1688)

<br>

## 5. 실험 결과 
![image](https://github.com/seoeunhyo/Implementation-of-calculation-system-using-YOLOv5-at-unmanned-store/assets/93567740/c3aab409-fa97-4f0c-924e-c5ef0e9eeae4)
![image](https://github.com/seoeunhyo/Implementation-of-calculation-system-using-YOLOv5-at-unmanned-store/assets/93567740/d5751c3f-c124-49f5-bdad-20b26cf1c260)
![image](https://github.com/seoeunhyo/Implementation-of-calculation-system-using-YOLOv5-at-unmanned-store/assets/93567740/0de2fbcd-2971-48df-89ce-ae08a8722666)

<br> 

### 6. 결론 

- 바코드를 이용한 기존 무인 점포 셀프 계산대에 비해 **계산속도 약 20~30% 증가** 
- 객체의 외관과 특징을 이용해 어떤 각도에서도 객체 인식 가능


- 향후 과제:

	- 광량 문제 
	 청명한 날씨에 자연광이 객체를 비추는 상태에서 객체의 상(像)이 카메라에 입사될 경우 개선된 시스템이 인식 어려움 

	- 실제 무인 시스템 구현 
	본 연구의 무인계산 시스템에 재고관리 시스템이나 판매 수 예측 시스템을 추가해 실제 무인계산 시스템을 구현 

