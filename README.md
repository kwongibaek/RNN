# RNN

-Sequential data

:텍스트나 time series data와 같이 순서에 의미가 있는 데이터 

-RNN (Recurrent Neural Network)

: 일반적인 fully connected neural network에 이전 데이터의 처리 결과가 순환되는 고리 추가 

(뉴런의 출력이 다시 자기 자신으로 전달)

<-> feedfoward neural network

: CNN이나 fully connected neural network처럼 입력 데이터의 흐름이 앞으로만 전달되는 신경망

--> time step : 샘플을 처리하는 한 단계

--> layer가 아니라 cell이라고 지칭 

(하나의 cell로 층 표현) = 뉴런 모두 표시 X

--> cell의 output = hidden state 라고 지칭

--> hyperbolic tangent를 활성화 함수로 주로 사용 

(-1 부터 1 범위의 함수)

--> feedfoward 신경망과 달리 이전 timestep의 hidden state에 곱해지는 가중치 존재 

(모든 time step에 적용되는 가중치는 1개)

(이전 time step의 hidden state는 다음 time step의 뉴런에 fully connected)

--> sample 마다 2개의 차원을 가짐 

(시퀀스의 길이 = 타임스텝, 단어표현) 

--> 최종 셀이 아닐 경우에는 타임 스텝의 모든 hidden state를 출력, 최종 셀의 경우 마지막 time step의 hidden state를 출력 

--> simpleRNN의 경우 timestep이 길어질수록 gradinet vanishing이 발생 

=> 먼 과거 정보 기억X

sol) LSTM, GRU, Transformer (attention을 통해)

--> Dropout 층을 통해 overfitting 막을 수 있음 

(이때, RNN에서는 cell의 입력을 dropout하거나 recurrent되는 hidden state를 dropout 할 수 있음)
