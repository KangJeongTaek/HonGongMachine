# 혼자 공부하는 머신러닝 + 딥러닝

## Chapter 01 나의 첫 머신러닝 - 이 생선의 이름은 무엇인가요?


### 01-1 인공지능과 머신러닝, 딥러닝
- 인공지능
    - 인공일반지능, 강인공지능
    - 약인공지능 (현실에서 우리가 마주하고 있는 인공지능)
- 머신러닝
    - 규칙을 일일히 프로그래밍하지 않아도 자동을 데이터에서 규칙을 학습하는 알고리즘을 연구하는 분야
- 딥러닝
    - 많은 머신러닝 알고리즘 중에 인공 신경망을 기반으로 한 방법들의 통칭
    - 주요 라이브러리
        1. 구글의 텐서플로
        2. 페이스북의 파이토치

### 01-2 코랩과 주피터 노트북
- 구글 코랩
    - 웹 브라우저에서 무료로 파이썬 프로그램을 테스트하고 저장할 수 있는 서비스
    - [구글코랩 사이트](https://colab.research.google.com/)
    - **단 기록을 남기기 위해 저자는 vscode 주피터 노트북을 이용할 예정**

### 01-3 마켓과 머신러닝
- [주피터노트북 파일](notes/BreamAndSmelt01.ipynb)

#### 키워드로 끝내는 핵심 포인트
- 특성 : 데이터를 표현하는 하나의 성질 EX. 생선 데이터 각각을 길이와 무게 특성으로 나타냄
- 훈련 : 머신러닝 알고리즘이 데이터에서 규칙을 찾는 과정. 사이킷런에서는 fit() 메서드
- k-최근접 이웃 알고리즘 : 가장 간단한 머신러닝 알고리즘 중 하나. 
- 모델 : 머신러닝 프로그램에서 알고리즘이 구현된 객체
- 정확도 : 정확한 답을 몇 개 맞혔는지를 백분율로 나타낸 값

#### 핵심 패키지와 함수
- matplotlib
    - scatter() : 산점도 그리기 2개의 매개변수로 x축 값과 y축 값을 전달
- scikit-learn
    - KNeighborsClassifier() : k-최근접 이웃 분류 모델을 만드는 사이킷런 클래스
    - fit() : 사이킷런 모델 훈련 메서드. 매개변수로 훈련에 사용할 특성과 정답 데이터
    - predict() : 사이킷런 모델을 훈련하고 예측할 때 사용하는 메서드
    - score() : 훈련된 사이킷런 모델의 성능 측정. 매개변수로 특성과 정답 데이터를 전달

## Chapter 02 데이터 다루기 - 수상한 생선을 조심하라!

### 02-1 훈련 세트와 테스트 세트
- [주피터노트북 파일](notes/BreamAndSmelt02.ipynb)
- 지도 학습과 비지도 학습
    - 지도 학습 : 훈련하기 위한 데이터와 정답이 필요요
        - 입력 : 지도 학습에서의 데이터
        - 타깃 : 지도 학습에서의 정답
        - 입력과 타깃을 아울러 훈련 데이터라고 한다. 
    - 비지도 학습 : 타깃 없이 입력 데이터만 사용. 정답이 없으므로 무언가를 맞힐 수는 없으나, 데이터를 잘 파악하거나 변형하는 데 도움을 준다.
    - 강화 학습 : 타깃이 아니라 알고리즘이 행동한 결과로 얻은 보상을 사용해 학습 (이 책에서는 다루지 않음)

- 훈련 세트와 테스트 세트
    - 테스트 세트 : 평가에 사용하는 데이터
    - 훈련 세트 : 훈련에 사용하는 데이터

- 샘플링 편향
    - 훈련하는 데이터와 테스트하는 데이터에는 데이터가 골고루 섞여 있어야 한다.
    - 샘플링 편향 : 일반적으로 훈련 세트와 테스트 세트에 샘플이 골고루 섞여 있지 않다는 의미

- 넘파이
    - 파이썬의 대표적인 배열 라이브러리
#### 키워드로 끝내는 핵심 포인트
- 지도 학습 : 입력과 타깃을 전달하여 모델을 훈련한 다음 새로운 데이터를 예측하는 데 활용
- 비지도 학습 : 타깃 데이터가 없음. 따라서 예측이 아니라 입력 데이터에서 어떤 특징을 찾는데 주로 활용
- 훈련 세트 : 모델을 훈련할 때 사용하는 데이터. 보통 훈련 세읕가 클수록 좋다. 따라서 테스트 세트를 제외한 모든 데이터를 사용
- 테스트 세트 : 전체 데이터에서 20%~30%를 테스트 세트로 사용하는 경우가 많다.

#### 핵심 패키지와 함수
- numpy
    - seed() : 난수를 생성하기 위한 정수 초깃값 지정.
    - arrange() : 일정한 간격의 정수 또는 실수 배열을 생성

### 02-2 데이터 전처리
- [주피터노트북 파일](notes/BreamAndSmelt03.ipynb) 참조

#### 키워드로 끝나는 핵심 포인트
- 데이터 전처리 : 머신러닝 모델에 훈련 데이터를 주입하기 전에 가공하는 단계
- 표준점수 : 훈련 세트의 스케일을 바꾸는 대표적인 방법 중 하나
- 브로드캐스팅 : 크기가 다른 넘파이 배열에서 자동으로 사칙 연산을 모든 행이나 열로 확장하여 수행하는 기능

#### 핵심 패키지와 함수
- scikit-learn
    - train_test_split() : 훈련 데이터를 훈련 세트와 테스트 세트로 나누는 함수. 여러 개의 배열 전달 가능. 테스트 세트로 나눌 비율은 test_size 매개변수에서 지정 (기본값 0.25)
    - kneighbors() : k-최근접 이웃 객체의 메서드. 입력한 데이터에 가장 가까운 이웃을 찾아 거리와 이웃 샘플의 인덱스를 반환

## Chapter 03 회귀 알고리즘과 모델 규제 - 농어의 무게를 예측하라!

### 03-1 k-최근접 이웃 회귀
- [주피터 노트북 파일](notes/perch01.ipynb)
- k-최근접 이웃 회귀
    - 지도 학습 일고리즘은 크게 분류와 회귀로 나뉨
        - 분류 : 샘플을 몇 개의 클래스 중 하나로 분류
        - 회귀 : 임의의 어떤 숫자를 예측 (정해진 클래스가 없고 임의의 수치를 출력)

#### 키워드로 끝내는 핵심 포인트
- 회귀 : 임의의 수치를 예측하는 문제
- k-최근접 이웃 회귀 : k-최근접 이웃 알고리즘을 사용해 회귀 문제를 품. 타깃값의 평균
- 결정계수(R<sup>2</sup>) : 대표적은 회귀 문제의 성능 추정 도구. 1에 가까울수록 좋고, 0에 가까울수록 나쁘다.
- 과대적합 : 모델의 훈련 세트 성능이 테스트 세트 성능보다 훨씬 높을 때 발생.
- 과소적합 : 훈련 세트와 테스트 세트 성능이 모두 낮거나 테스트 세트 성능이 오히려 더 높을 때 발생.

#### 핵심 패키지와 함수
- scikit-learn
    - KNeighborsRegressor : k-최근접 이웃 회귀 모델을 만드는 사이킷런 클래스.
    - mean_absolute_error() : 회귀 모델의 평균 절댓값 오차를 계산. 첫 번째 매개변수는 타깃, 두 번째 매개변수는 예측값을 전달.
- numpy
    - reshape() : 배열의 크키를 바꾸는 메서드

### 03-2 선형 회귀
- [주피터 노트북 파일](notes/perch02.ipynb)

#### 키워드로 끝내는 핵심 포인트
- 선형 회귀 : 특성과 타깃 사이의 관계를 가장 잘 나태는 성형 방정식을 찾는다. 특성이 하나면 직선 방정식이 된다.
    - 선형 회귀가 찾은 특성과 타깃 사이의 관계는 선형 방정식의 계수 또는 가중치에 저장된다. (기울기와 절편)
- 모델 파라미터 : 선형 회귀가 찾은 가중치처럼 머신런링 모델이 특성에서 학습한 파라미터를 의미
- 다항 회귀 : 다항식을 사용하여 특성과 타깃 사이의 관계를 나타낸다. 이 함수는 비선형일 수 있지만 여전히 선형 회귀로 표현할 수 있다

#### 핵심 패키지와 함수
- LinearRegression : 사이킷런의 선형 회귀 클래스
     -coef_ 속성 : 특성에 대한 계수를 포함한 배열 / 크기는 특성의 개수와 같다.
     - intercept_ 속성 : 절편편

### 03-3 특성 공학과 규제
- [주피터 노트북 파일](notes/perch03.ipynb)

#### 키워드로 끝내는 핵심 포인트
- 다중 회귀 : 여러 개의 특성을 사용하는 회귀 모델. 특성이 많으면 선형 모델은 강력한 성능을 발휘한다.
- 특성 공학 : 주어진 특성을 조합하여 새로운 특성을 만드는 일련의 작업 과정
- 릿지 : 규제가 있는 선형 회귀 모델 중 하나. 선형 모델의 계수를 작게 만들어 과대적합을 완화시킨다.
- 라쏘 : 또 다른 규제가 있는 선형 회귀 모델. 릿지와 달리 계수 값을 아예 0으로 만들 수도 있다.
- 하이퍼파라미터 : 머신러닝 알고리즘이 학습하지 않는 파라미터. 사람이 사전에 지정해야 한다.대표적으로 릿지와 라쏘의 규제강도(alpha) 파라미터.

#### 핵심 패키지와 함수
- pandas
    - read_csv() : CSV 파일을 로컬 컴퓨터나 인터넷에서 읽어 판다스 데이터프레임으로 변환하는 함수
- scikit-learn
    - PolynomialFeatures : 주어진 특성을 조합하여 새로운 특성을 만든다. 
        - degree는 최고 차수를 설정. 기본값은 2
    - Ridge : 규제가 있는 회귀 알고리즘인 릿지 회귀 모델을 훈련
        - alpha 매개변수로 규제의 강도를 조절. 클수록 규제가 강해진다.
    - Lasso : 규제가 있는 회귀 알고리즘인 라쏘 회귀 모델을 훈련.
        - alpha : Ridge와 동일


## Chapter 04 다양한 분류 알고리즘 - 럭키백의 확률을 계산하라!

### 04-1 로지스틱 회귀
- [주피터 노트북 파일](notes/LuckyBag.ipynb)

#### 키워드로 끝내는 핵심 포인트
- 로지스틱 회귀 : 선형 방정식을 사용한 분류 알고리즘. 선형 회귀와 달리 시그모이드 함수나 소프트맥스 함수를 사용하여 클래스 확률을 출력할 수 있다
- 다중 분류 : 타깃 클래스가 2개 이상힌 분류 문제. 로지스틱 회귀는 다중 분류를 위해 소프트맥스 함수를 사용하여 클래스를 예측한다.
- 시그모이드 함수 : 선형 방정식의 출력을 0과 1 사이의 값으로 압축하며 이진 분류를 위해 사용한다.
- 소프트맥스 함수 : 다중 분류에서 여러 선형 방정식의 출력 결과를 정규화하여 합이 1이 되도록 만든다.

#### 핵심 패키지와 함수
- scikit-learn
    - LogisticRegression : 선형 분류 알고리즘인 로지스틱 회귀를 위한 클래스