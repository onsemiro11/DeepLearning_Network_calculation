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

## Dense Layers

Layer는 서로 다른 Parameter(Weight, Bias)들을 가지고 있는 Parametric Function들의 모임이다.

즉, Neuron들의 집합이라고 생각면된다. 다양한 Neuron들이 하나의 층을 형성하고 그것을 layer라고 부른다.

그리고, Dense Layers는 모든 입력값(x1,x2,x3,x4,xli)가 각각의 뉴런에 모두 들어가는 것을 말한다.

- Input vector (vector X transposed)가 ℓI(엘아이)개 있기 때문에 Weight(vector W)도 ℓI개 있어야한다.
> 그 이유는 행렬곱의 개념을 가져와 실행하기 때문인데, 행렬곱은 XY인 경우에 X의 열의 개수와 Y의 행의 개수가 같아야 각 원소끼리 곱하면서 더해져가기 때문이다.
 
- Neuron이 ℓ1개 있으면 weight 자체, bias 자체도 ℓ1개 있다.
> 그 이유는 각 neuron에 각 weight와 bias가 할당되어 있을 거기 때문이다. 이부분이 하나의 layer에서는 당연한 말이라고 생각되겠지만, 층이 깊어질 수록 헷갈려질 수 있다. 유의해놓자.

- Input 값 X의 열 개수와는 관계없이 결괏값 a vector는 neuron의 개수 ℓ1과 연관된 vector (1,ℓ1) 형태다.
> 이유는 X ∈ R(1xℓI) 가 들어오면, 우선 W(metrix) ∈ R(ℓIxℓ1)와 행렬곱을 실행하여, bias(vector transposed) ∈ R(1xℓ1)와 더해주면, (1 x ℓI) * (ℓI x ℓ1) + (1 x ℓ1) = (1 x ℓ1)로 결괏값 a vector는 shape = (1 , ℓ1)가 된다.
 
- 결괏값 a는 X * W + b 의 결괏값 Z에 activation function인 g( ) 을 진행해줘서 나온 값이다.
