# Tensorflow 문법

### Placeholder

placeholder 자료형은 조금 특이하다. 선언 후 그 다음 값을 전달한다. 따라서 반드시
실행 시 데이터가 제공되어야 한다. 값을 전달한다고 되어 있는데 이는 데이터를
상수값을 전달함과 같이 할당하는 것이 아니라 다른 텐서(Tensor)를 placeholder에
맵핑 시키는 것.
외부데이터를 받아솨서 저장하는 변수. 
학습 데이터를 포함하는 변수

다른 tensor 를 할당하기 위해 사용, 할당할떄는 피딩(feeding)을 수행

y = x + 5 y=출력 x=는 입력 즉 플레이스홀더

placeholder(dtype, shape=None, name=None)
**dtype** : 데이터 타입을 의미하며 반드시 적어주어야 한다 플레이스 홀더에 저장되는
자료형.

**shape** : 입력 데이터의 형태를 의미한다. 상수 값이 될 수도 있고 다차원 배열의
정보가 들어올 수도 있다. ( 디폴트 파라미터로 None 지정 )배열의 차원을 의미

**name** : 해당 placeholder의 이름을 부여하는 것으로 적지 않아도 된다. ( 디폴트
파라미터로 None 지정 ) 플레이스 홀더의 이름을 의미

![A](https://user-images.githubusercontent.com/57824945/77319711-a28b3780-6d52-11ea-99d1-0e4c76555bfd.png)

[17.0]


위에서도 말했었지만, placeholder는 다른 텐서를 할당하는 것이라고 했다. 이를
할당하기 위해서는 feed dictionary 라는 것을 활용하게 되는데 세션을 생성할때
feed_dict의 키워드 형태로 텐서를 맵핑 할 수 있다.

위와 같이 선언 후 feed_dict 변수를 할당해도 되고 바로 값을 대입시켜도 무방하다.

placeholder는 여러 형태로 사용할 수 있다. 머신러닝에서는 다차원 배열 데이터가
많이 들어오게 되는데 어쨌든 배열의 형태가 값으로 들어가도 무방하다는 것이다.

![B](https://user-images.githubusercontent.com/57824945/77319722-a5862800-6d52-11ea-9da2-5db1a8e60a7b.png)

[ 11. 22. 33. 44. 55.]

허접하지만 이와 같이 Image Matrix(영상)의 정보와 각 라벨이 들어가 있다고
가정해보자..

크게 의미가 있는 코드는 아니지만 이와 같이 연산을 수행할 수 있다.

보통 데이터셋(DataSet) 정도의 거대 데이터 정보를 feed로 많이 주는 것으로
활용된다.

**tf.get_variable()** : 학습 중에 값이 계속 변하는 변수

**tf.random_uniform**(배열의 shape, 최소값, 최대값): 정규분포 난수 생성함수. [1], -
100, 100이면, -100에서 100 사이의 난수를 1개 만든다. 난수를 사용하는 중요한 이유는
최저 비용을 스스로 찾아가야 하는데, 시작 위치가 매번 달라짐에도 불구하고 항상 최저
비용을 찾는다는 것을 보여주기 위해서 이다.

### 변수 상수

import tensorflow as tf
a=tf.constant(1) //실제 어떤 텐서 자료를 반환, 1이라는 배열 텐서를
생성하여 a에 대입
b=tf.constant(2)
c=tf.add(a,b) //두 값을 더한것 저장
sess = tf.Session() //수식 만든 후 실제 수행을 위한흐름(sess) 필요
sess.run(c)


**Tensor란?** : 배열 차원의 갯수
rank type example
0 scalar [1]
1 vector [1,1]
2 matrix [[1,1],[1,1]]
3 3 tensor [[[1,1],1,1]],[[1,1],1[1]]]
n n tensor

tensor exmaple
- Grayscale image(흑백 사진)
(3, 5, 5) &lt;= (N image, rows, columns) 3 tensor !
- rgb color image(컬러 사진)
(3, 5, 5, 3) &lt;= (N image, rows, columns, (red, green, blue)) 4 tensor !
-rgb color video

(3, 5, 5, 5, 3) &lt;= (frames ,N image, rows, columns, (red, green, blue))
5 tensor!

## 주요함수
&lt;기본함수&gt;
tf.add : 덧셈 수행
tf.subtract : 뺼셈 수행
tf.multiply : 곱셈 수행
tf.truediv : 나눗셈의 몫
tf.mod : 나눗셈의 나머지
tf.abs : 절대값

&lt;자주 사용되는 함수&gt;
tf.negative : 음수 반환
tf.sign : 부호를 반환
tf.square : 제곱을 수행

tf.sqrt : 제곱근을 반환
tf.pow : 거듭제곱 수행
tf.maximum : 더 큰 값을 반환
tf.minimum : 더 작은 값을 반환
tf.exp : 지수 값을 계산
tf.log : 로그 값을 계산
tf.sin : 사인 값 계산
tf.cos : 코사인 값 계산
tf.tan : 탄젠트 값 계산

텐서 플로우 시스템 아키텍쳐
텐서플로우는 기본적으로 대규모 분산 학습 및 추론을 위한
라이브러리이다. 또한 개별 컴퓨터가 최적화된 성능에서 다양한
실험을 할 수 있도록 많은 기계학습 모델을 제공

텐서플로우는 기본적으로 크로스플랫폼 라이버러리. C API(C 언어가
core) 가 로우 레벨단에 존재하므로 프로그래머가 다양한 프로그래밍
언어를 이용해 소스코드를 작성할수 있도록 해줌

1.클라이언트
컴퓨터 연산 과정을 데이터 플로우 그래프 형태로 표현합니다
세션(Session)을 이용해 한 번의 그래프 실행 시작을 알릴 수 있습니다.
