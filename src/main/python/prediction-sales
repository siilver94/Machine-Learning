import tensorflow.compat.v1 as tf
tf.disable_v2_behavior()

xData = [1,2,3,4,5,6,7] #시간
yData = [25000, 55000, 75000, 110000, 128000, 155000, 180000] #하루 매출량
#random_uniform : 하나의 랜덤값 생성
W= tf.Variable(tf.random_uniform([1],-100,100))
#가설의 기울기,weight 가중치
b = tf.Variable(tf.random_uniform([1],-100,100)) #bias 성향
#x,y를 placeholder로 정의, 대표적인 형태, 틀 형태 생성
X=tf.placeholder(tf.float32)
Y=tf.placeholder(tf.float32)
#가설
H=W*X+b
cost = tf.reduce_mean(tf.square(H-Y)) #비용함수. reduce_mean: 평균값 구하기, 예측값-
실제값의 제곱
a=tf.Variable(0.01) #경사하강 알고리즘 에서 step 의 크기, 속도
optimizer = tf.train.GradientDescentOptimizer(a) #tensorflow에서 기본 제공하는 &#39;경사하강&#39;
라이브러리
train = optimizer.minimize(cost) #비용함수를 가장 적게 만드는 방향의 학습 방향
init = tf.global_variables_initializer() #변수 초기화
sess=tf.Session() #세션 정의
sess.run(init) #세션 초기화
for i in range(5001): #5000번 학습
sess.run(train, feed_dict={X:xData, Y: yData}) #x,y데이터 매칭
if i % 500 ==0: #500번 마다 학습 결과 출력
print(i,sess.run(cost, feed_dict={X: xData, Y : yData}), sess.run(W), sess.run(b))
print(sess.run(H, feed_dict={X :[8]}))


 <result>
0 4559978000.0 [10418.546] [2124.2642]
500 8688397.0 [25536.262] [1956.425]
1000 8633829.0 [25627.324] [1505.4911]
1500 8632678.0 [25640.592] [1439.7825]
2000 8632651.0 [25642.527] [1430.2045]
2500 8632655.0 [25642.805] [1428.8223]
3000 8632656.0 [25642.844] [1428.6338]
3500 8632657.0 [25642.848] [1428.6133]
4000 8632657.0 [25642.848] [1428.6133]
4500 8632657.0 [25642.848] [1428.6133]
5000 8632657.0 [25642.848] [1428.6133]
[206571.39]
