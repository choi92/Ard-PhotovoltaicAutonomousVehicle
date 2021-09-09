# 태양광자율주행자동차
이 프로젝트는 2020 서운고 태양광자율주행자동차부의 프로젝트입니다. 
## 소개
**태양광을 동력으로하는 자율주행 자동차를 제작**
* Level3 자율주행 자동차 제작
* 태양 전지로 리튬 전지 충전 후 리튬 전지를 동력으로 자동차 동작
* 자동으로 충전소를 찾는 알고리즘 설계
* 안드로이드 어플리케이션으로 자동차를 조종하며 초음파 센서로 장애물 회피

## 자율주행 자동차 제작
### 알고리즘 설계
![image](https://user-images.githubusercontent.com/65582244/132712312-4976347e-1d0c-4d59-97f4-4a5613b93dfb.png)

![image](https://user-images.githubusercontent.com/65582244/132712326-1f7b0949-9cdd-4ef2-b9ea-db05cdfe6fa2.png)

### 회로설계
![image](https://user-images.githubusercontent.com/65582244/132711887-71b3f8eb-a736-4754-8e31-7f4905a0a6e3.png)
- 3.7V, 2600mAh인 18650 리튬 이온 전지 2개를 이용하여 7.4V의 전원을 공급해준다.
- 하비 기어모터를 좌우에 각각 2개씩 연결한다.
- HC-06 블루투스 모듈을 이용해 블루투스 통신을 하도록 한다.
- 초음파 센서를 이용해 거리 측정을 한다.
- 초록 LED와 능동 부저를 통해 시동 on/off, 충전 대기 등의 상태를 알린다.
- CdS로 충전소의 레이저 신호를 수신한다.
- 홀 센서(hall censor)로 충전소에서 정확한 위치에서 충전할 수 있도록 한다.
- 18650 리튬 이온 전지에 30Ω저항으로 부하를 걸어서 실제 전기에너지를 내는 힘을 체크하여 배터리 잔량을 측정한다.

### 자동차 제작
![image](https://user-images.githubusercontent.com/65582244/132712210-c290b118-2e66-4ba4-bf96-da07c881868e.png)
- 제자리 선회, 중립조향(Neutral Steering)이 아닌 일반적인 자동차와 같은 회전 방식이다.

### 소스 코드
https://github.com/choi92/Ard-PhotovoltaicAutonomousVehicle/blob/master/PhotovoltaicAutonomousVehicle_Car.ino

## 자동차 조종 어플리케이션 제작
### 알고리즘 설계
- 자동차와 블루투스 통신을 할 수 있도록 한다.
- 십자키를 이용하여 자동차가 주행할 수 있도록 한다.
- 자동차의 시동을 켜고 끌 수 있도록 하고 상태를 표시한다.
- 18650 리튬 이온 전지의 배터리 잔량을 표시하고 직관적으로 볼 수 있도록 색을 이용하여 표시한다.
- 언제든지 충전할 수 있도록 충전버튼을 만든다.

### 블록(소스 코드)
![image](https://user-images.githubusercontent.com/65582244/132712679-9d755612-9cd1-453f-9b69-07ac7f2d5593.png)
![image](https://user-images.githubusercontent.com/65582244/132712694-73621db4-5bf5-4ccd-9c7b-a33dae031439.png)
![image](https://user-images.githubusercontent.com/65582244/132712704-c349a17c-065b-4f98-b1f6-e221e19386b5.png)

### 구동 모습
![image](https://user-images.githubusercontent.com/65582244/132712788-53e8af5c-e032-4cc1-8a74-e6caf6ad3764.png)

## 충전소 제작
### 알고리즘 설계
![image](https://user-images.githubusercontent.com/65582244/132712973-0681effc-c2c7-447b-837b-e62a38ad574d.png)

### 회로 설계
![image](https://user-images.githubusercontent.com/65582244/132713046-bf5cd5c1-712e-49f6-84d7-1ce565b229d2.png)
- 사운드 센서와 레이저 모듈, 서보모터를 알맞게 연결
- 서보모터를 구동할 수 있게 9V전원 연결

### 충전소 제작
![image](https://user-images.githubusercontent.com/65582244/132713166-f4ac51a2-7835-49f9-a3f4-5fd2ccde7eac.png)
![image](https://user-images.githubusercontent.com/65582244/132713179-38612317-a234-4267-89a9-b99c9196e4f5.png)
- 태양광 패널을 이용하여 전기를 생산하고 생산된 전  기를 리튬이온전지 18650에 공급
- 사운드 센서를 이용해 자동차가 송신하는 충전 대기  신호를 수신 할 수 있도록 함
- 서보모터가 레이저를 달고 돌아가며 레이더 역할을 하여 레이저를 이용해 자동차로 충전소의 위치를 송신하여 자동차가 충전소의 위치를 알고 어느 방향으로 가야하는지 알려줌
- 3D프린터를 이용하여 충전소의 전력 공급을 원활하게 하고 자석을 달아 자동차의 정지 지점을 알려줌

### 소스 코드
https://github.com/choi92/Ard-PhotovoltaicAutonomousVehicle/blob/master/PhotovoltaicAutonomousVehicle_ChargeCenter.ino

## 구동
![image](https://user-images.githubusercontent.com/65582244/132714568-614c8983-aa7b-4b90-90ca-1c400c559996.png)

***

## 리튬이론전지 배터리 효율 개선 방안 탐구
### 리튬이온전지의 열관리 필요성
리튬이온전지의 성능 및 안전성은 온도에 상당한 영향을 받는다. 리튬이온전지의 저온 작동 시에는 전극활물질의 활성도와 리튬 이온의 확산계수가 낮아짐으로써 전지의 성능이 급격하게 저하한다. 온도에 따른 성능 감소와 심각한 사고를 예방하기 위해서는 리튬이온전지가 적절한 온도 범위 내에서 반드시 가동 및 보관되어야 하고, 이를 위해 적절한 열관리 기기 또는 시스템이 필요하다. 리튬이온전지의 사용 가능 온도는 0\~60 ºC이지만, 최적의 성능을 위해서는 15\~40 ºC 사이에서의 가동이 권장된다.

### 리튬이온전지의 온도에 따른 효율 탐구
50℃, 80℃ 열풍기, 0℃ 얼음, -50℃ 드라이 아이스를 이용헤 온도에 따른 전압을 비교해본다.

 |-50℃|0℃|상온|50℃|80℃
 ---|---|---|---|---|---
평균 전압(V)|3.585|3.591|3.6|3.602|3.606

이러한 결과를 보면 차이가 크진 않지만 적당한 온도에서 전압값이 높게 측정된다.

### 리튬이온전지의 효율 개선 방안 탐구
- 공랭식 방법
외부 공급장치를 이용하여 전지 주변으로 유동을 발생시켜서 온도를 낮추거나  공기의 밀도 차를 이용한 부력을 통해 공기를 순환시켜서 온도를 낮추는 방법이다.
- 수랭식 방법
실리콘 기반의 오일 또는 미네랄오일 이나 냉각판(cold plate), 냉각관(cold tube), 냉각덮개(cold jacket) 등을 사용하여 냉각수와 함께 배터리를 식혀서 온도를 낮추는 방법이다.

하지만 우리가 실험할 자동차는 실제 자동차와 달리 전압을 많이 필요로 하지 많아 발열이 되지 않으므로 온도를 낯추는 것이 오히려 독이 될 수 있다. 따라서 우리는 오히려 온도를 유지하여 온도가 내려가 배터리 효율이 낮아지지 않도록 할 것이다.
얼음을 이용해 전지의 온도가 낮아진 상태에서 기다린 다음, 전지의 효율이 어느 정도 떨어졌을 때 전지 외부에 재료들로 감싸서 보온 효과를 내도록 한 실험을 진행하였다.
그 결과 열전도도가 낮은 랩(0.03W/mk), 종이컵 종이(0.45W/mk), A4 종이(0.50W/mk), 비닐(0.13~0.17W/mk), 플라스틱(0.31W/mk), 알루미늄 호일(235W/mk) 순으로 평균전압이 높게 나왔다. 따라서 우리는 보온 효과가 높은 랩을 전지에 감싸서 효율을 높일 것이다.
