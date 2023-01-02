# DeepLearning Network Calculation

## Affine_Function

- Affine Transformation을 활용한 함수다. 
- Affine Transformation은 선형변환(Y = WX)에서 +b를 추가하여 벡터에 위치 이동의 개념을 추가시킨 것이다.
- 아핀 공간은 벡터에 위치의 개념을 추가시킨 것이다.
 
          Linear Transformation -> Y = WX                               Affine Tarnsformation -> Y = WX + B
 
Affine Function은 데이터와 실제값 사이의 규칙을 찾는 과정을 거쳐 만들어진 식이다.
즉, 주어진 훈련데이터로 입력데이터인 X와 실제 값인 Y간의 규칙을 찾아 적당한 W와 B값을 할당 시켜 만들어진 식이라는 것이다.

## Artificial Neuron

Artificial Neuron이란, 신경해부학적 사실을 토대로 하여 만든 인공신경망 기본구성요소로, 단순한 연산기능을 가지고 있는 수많은 인공뉴런이 서로 연결되어 정보를 저장하고 처리한다는 개념이다.

<img width="534" alt="image" src="https://user-images.githubusercontent.com/49609175/210253075-9c93a86c-8295-4cb6-bbef-370b93a8ef10.png" width="500" height="300">

위 그림은 Artificial Neurons의 전체 과정으로 affine function과 activation function의 파트로 나눠지고 affine function에서 계산된 값을 activation function에서 한번더 연산을 하는 과정이다.
