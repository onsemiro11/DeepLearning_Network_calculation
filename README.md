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

## Activation Function

Activation Function은 affine function에서 만들어진 식을 통해 나온 Y값을 sigmoid/tanh/relu 등의 식에 대입하여, 보다 정렬된 값으로 변형시켜주는 식이다.
 
<span style="color:red">그러면 왜 우리는 Activation Function을 사용해야하는가?</span>
 
-선형시스템이 아닌 비선형 시스템으로 변형시키기 위해서다. 이렇게 말하면 잘 와닿지 않을 것이다.
 
선형시스템은 한계가 있다. XOR문제는 다들 알 것이다.
선형시스템은 AND와 OR문제는 해결할 수 있지만, XOR과 같은 non-linear한 문제는 해결할 수 없다는 한계가 있다.
그리고, 선형시스템은 아무리 layer들을 쌓아 깊게 구현한다고 해도 f(ax+by)=af(x)+bf(y)의 성질 때문에 결국 하나의 linear연산으로 나타낼수 있다.
이에 대한 해결책이 Activation Function을 통해 출력값을 비선형 시스템으로 만드는것이다.
 
sigmoid 함수
 
나중에 linear regression에서 한번더 정리할 것이다. odds의 개념과 logit의 개념으로 구체적으로 설명하겠다.
분류에서 주로 사용되고 확률로서의 역할을 하는 값으로 변환시킨다.

sigmoid function
tanh 함수
 
쌍곡선 함수중 하나로 x가 양의 무한으로 갈때, 1로 수렴하고 x가 음의 무한으로 갈때, -1로 수렴한다.
시그모이드 함수와 거의 유사하다. 데이터의 평균이 0.5가 아닌 0이라는 차이밖에 없지만 대부분의 경우 시그모이드보다 성능이 좋다.

tanh() function
relu 함수
 
대부분의 경우 일반적으로 relu의 성능이 가장 좋기때문에 사용한다.

relu function

