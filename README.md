

# YOLOv5를 이용한 무인 점포 계산 시스템의 구현 
> 2022-1학기 빅데이터/인공지능 융합전공 캡스톤 디자인 <br>
> YOLOv5를 이용하여 바코드가 아닌 이미지 인식을 통해 계산할 수 있는 시스템 구현 <br>
> 🌟2022 교내 캡스톤 디자인 경진대회 장려상 수상🌟
<br>

## 1. 소개 
> 진행 기간: 2022. 03 ~ 2022. 06 <br>


![image8](https://github.com/seoeunhyo/Implementation-of-calculation-system-using-YOLOv5-at-unmanned-store/assets/93567740/5cd8c925-d8bd-4178-904b-86485405f936) ![image12](https://github.com/seoeunhyo/Implementation-of-calculation-system-using-YOLOv5-at-unmanned-store/assets/93567740/df8e37e6-ab02-4a35-a187-29e766376e89)

- 기존 바코드 인식을 통해 물품을 계산하는 시스템은 이용자가 직접 바코드를 찾아 스캔해야 하는 불편함이 있다. 
- 본 프로젝트에서는 YOLOv5를 이용하여 바코드가 아닌 이미지 인식을 통해 계산할 수 있는 시스템을 구현하였다. 
- 초기 이미지 학습은 웹 크롤링과 직접 수집한 데이터를 이용하였고, OpenCV를 이용하여 별도의 라벨링 없이 자동으로 라벨링 해줄 수 있는 물품 등록기능을 추가하였다. 
- 본 프로젝트를 통해 개선된 시스템은 **기존 결제 시스템보다 결제 시간이 약 20% 단축**되었다.


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
<img width="583" alt="image" src="https://github.com/seoeunhyo/YOLOv5-Project/assets/93567740/2a8a81da-cd3f-43e9-b76b-7aa9cb055d27">

<br>
<br> 
<br>

## 4. 문제 해결 방법

**바코드를 인식 할 필요 없고, 데이터를 추가하는 과정이 자동화 된 무인 셀프 계산대를 고안**

1. 시중에서 판매하는 아이스크림 이미지를 학습데이터로 이용 <br>
   *(본 프로젝트의 경우 인식하는 물품의 예를 아이스크림으로 함)*  <br>
막대 모양(bar), 고깔 모양(Corn), 컵 모양(Cup) 각각 두 개씩 선정

3. 새로운 물품 등록, 물품 인식 및 계산 그리고 프로그램 종료 기능 제공
<br>


### 4.1 새로운 물품 추가의 경우 
<br> 
<img width="832" alt="image" src="https://github.com/seoeunhyo/YOLOv5-Project/assets/93567740/df36e0f6-6b38-4845-98d0-4ecd3ba4144a">

<br><br><br>

- 새로운 상품 등록 기능을 설정하면 카메라에 물품을 위치 시킬 범위가 표시됨
  - 라벨링 작업을 없애기 위해 물품의 좌표를 지정한 것 <br> 
    <img width="187" alt="image" src="https://github.com/seoeunhyo/YOLOv5-Project/assets/93567740/d7d20eb7-d45b-4d8a-9fe0-52379d78e7a0">
<br>

- 물품 등록 화면을 끝내면 이미지 증강과 이미지 데이터, 라벨 데이터를 생성 <br>
<img src="https://github.com/seoeunhyo/YOLOv5-Project/assets/93567740/90634f6e-148f-4394-b59a-c1a7efe14a0d" width="300" height="350"/>
<br><br>

- 물품의 이름을 사용자로부터 입력 받고, yaml의 클래스 번호 및 물품 이름 추가 <br><br>
![image](https://github.com/seoeunhyo/YOLOv5-Project/assets/93567740/72016d41-3cbf-4bbc-8efd-4cf82e048905)

<br>


### 4.2 물품 인식의 경우 
<br>

- 아이스크림 7종류(테스트를 위한 그 외 1종류 추가)에 대해 크롤링과 직접 수집한 이미지 약 2,900장을 학습 데이터로 사용
- 라벨링<br>
	<img src="https://github.com/seoeunhyo/YOLOv5-Project/assets/93567740/ac78c20f-a44c-48ed-89e5-02fa8bdd8f8c" width="320" height="300"/>
	<br>
- 에폭 50으로 학습 진행 <br>
	<img src="https://github.com/seoeunhyo/YOLOv5-Project/assets/93567740/eb0555f9-f6d3-4701-878b-aba6829db507" width="550" height="300"/>
<br>

### 4.3 물품 계산의 경우 
<br>

![image](https://github.com/seoeunhyo/YOLOv5-Project/assets/93567740/49d5f953-c0fb-42c9-b5c6-8679212f0ee9)

<br>
<br>

## 5. 실험 결과 
<img width="542" alt="image" src="https://github.com/seoeunhyo/YOLOv5-Project/assets/93567740/6f8e2b77-b323-4e56-a79e-e8550b5d0c79">

<br>

<img width="524" alt="image" src="https://github.com/seoeunhyo/YOLOv5-Project/assets/93567740/09189401-eb30-406d-a692-8d0c7aea4ecf">

<br><br>

### 기존 방식과 개선된 방식의 차이
<br><br>
<img width="573" alt="image" src="https://github.com/seoeunhyo/YOLOv5-Project/assets/93567740/6f11505c-64c8-415f-a673-f2febc439027">


<br> <br><br>

### 6. 결론 

- 바코드를 이용한 기존 무인 점포 셀프 계산대에 비해 **계산속도 약 20~30% 증가** 
- 객체의 외관과 특징을 이용해 어떤 각도에서도 객체 인식 가능


- 향후 과제:

	- 광량 문제 <br>
	 청명한 날씨에 자연광이 객체를 비추는 상태에서 객체의 상(像)이 카메라에 입사될 경우 개선된 시스템이 인식 어려움 

	- 실제 무인 시스템 구현 <br>
	본 연구의 무인계산 시스템에 재고관리 시스템이나 판매 수 예측 시스템을 추가해 실제 무인계산 시스템을 구현 

