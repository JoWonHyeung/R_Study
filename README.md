# R

## 3/15

- #### Boolean값 비교

     Javascript: true, false

     R: TRUE, FALSE, T, F

     Python: True, False

## 3/16

rm : 제거 함수

unique : 벡터에 저장된 데이터의 종류를 알 수 있는 함수. factor 자료형의 데이터형을 알기 위한 levels 함수와 같은 기능을 한다.

is.matrix, is.data.frame : 데이터셋이 매트릭스인지 데이터프레임인지 확인하는 함수

### 벡터

max : 벡터내에서 최대값 출력

min : 벡터내에서 최소값 출력

mean : 벡터내 평균

sum : 벡터내 원소 합

seq(시작, 종료, 간격) : 일정한 간격의 숫자로 이루어진 벡터

         ex) seq(1,10,3) -> 1, 4, 7, 10 출력
         
rep(반복대상값, times=반복횟수) : 반복된 숫자로 이루어진 벡터

         ex) rep(1,times=5) -> 1,1,1,1,1 출력

             rep(1:3,times=2) -> 1,2,3,1,2,3 출력
             
             rep(1:3,each=2) -> 1,1,2,2,3,3 출력
             
names : 벡터 값들의 이름을 확인하거나 이름을 지정할 때 사용한다.
          
rev : 역순 출력

range : 최소, 최대 출력

sort(x, decreasing = TRUE) : 정렬, 정렬 순서의 default는 오름차순

order : 정렬된 index 출력

         ex) x <- order(10,20,7,14,15) 
             3 1 4 5 2 출력 -> 가장 작은 값인 7은 벡터 3번째에 존재한다.
             
length : 벡터에 저장된 값들의 개수

which : 조건에 맞는 특정 위치들을 찾을 수 있다.

which.max : 벡터내에서 가장 큰 값의 index값을 반환

which.min : 벡터내에서 가장 작은 값의 index값을 반환한다.

sample(벡터, 몇 개를 뽑을지, replace=복원 추출 or 비복원 추출) : 랜덤값 출력, replace의 default 값은 False

paste (..., sep = " ", collapse = NULL) : 나열된 원소 사이에 공백을 두고 결과값을 출력합니다.

paste0(..., collapse = NULL) : 나열된 원소 사이에 공백없이 출력합니다.

summary : 기술통계함수

```R
mat[1,1,drop=F] #메트릭스 형태를 유지하려면 drop=F 설정
```

### 메트릭스

maxtrix(data, nrow, ncol, byrow, dimname) : 행렬 생성 함수, 행부터 채울려면 byrow = True로 설정
          
          ex) matrix(1:8, nrow =2)
              2 x 4 행렬 생성, default는 열먼저 채우고 행을 채운다.
              만약 원소의 개수가 맞지 않으면 처음 원소로 채워진다.   

dim : 행렬 차원 반환

colnames, rownames : 행과 열에 이름을 붙인다.

rbind, cbind : 백터들을 모아서 메트릭스 생성을 가능하게 하는 함수

t() : 전치행렬로 변환

### Array (3차원)

원소의 개수를 무조건 맞춰야 한다.
```R
a1 <- array(1:30, dim=c(2,3,5))
```

## 3/17

### factor

factor는 문자형 데이터가 저장되는 벡터의 일종으로, 저장되는 문자값들이 어떠한 종류를 나타내는 값일 때 사용된다. factor을 summary하면 각 Level별 개수를 count한다. factor은 사전에 정의된 값 외에 다른 값들은 입력하지 못하도록 한다. 입력하면 NA값이 대입된다.

levels : factor에 저장된 값의 종류를 출력한다.

as.integer() : 저장된 문자값을 숫자로 바꾸어 분석 작업에 활용할 수 있다. 바꾸는 방법에는 정해진 규칙이 있다. levels 함수를 통해 출력된 문자값들의 순서가 바로 변환될 숫자이다.

### DataFrame

DataFrame은 매트릭스와 마찬가지로 2차원 형태의 데이터를 저장하고 분석하는데 사용되는 자료구조이다. 매트릭스와의 차이는 서로 다른 종류의 값이 함께 저장된다는 것이다.

data.frame() : DataFrame생성

View() : DataFrame을 좀 더 시각적으로 보여주는 함수 

subset() : 변수 선택및 조건에 맞는 데이터를 추출하는데 사용된다. 

nrow, ncol, dim : 행,열 개수 확인

head, tail : 데이터셋의 앞,뒤를 출력하는 함수
```R
#아래 2줄 코드는 같은 결과를 출력한다. subset은 df 변수명을 생략해도 되고, 아래 코드 같은 경우는 생략하면 안된다.
subset(emp, sal>=2000 & sal<=3000, c("ename","sal"))
emp[emp$sal>=2000 & emp$sal <=3000, c("ename","sal")]
```
is.na() : 결측치를 check하는 함수

colnames, rownames : 행과 열에 이름을 붙인다.

test$colname : colname에 해당하는 컬럼 데이터들을 출력한다.

### class() vs mode()

class : 데이터 구조 확인, 데이터 구조에는 vector, matrix, data.frame, list, factor이 있다.

mode : 객체의 내부적 타입 확인

### Data에서 종류별로 개수를 count하는 방법

1. table 함수를 사용한다

2. summary(factor(score$result))처럼 factor로 바꿔서 실행할 것

### 연산
```R
num1 / num2    # 나눗셈
num1 %% num2   # 나머지 값
num1 %/% num2  # 몫
```
## 3/20

### 데이터프레임에만 적용되는 열 추출 방법

```R
iris[,'Species'] #결과가 벡터-매트릭스, 데이터프레임 모두 가능
iris[,5] #결과가 벡터-매트릭스, 데이터프레임 모두 가능
iris['Species'] #결과가 데이터프레임-데이터프레임만 가능, 데이터프레임으로 반환
iris[5] #결과가 데이터프레임-데이터프레임만 가능, 데이터프레임으로 반환
iris$Species #결과가 벡터-데이터프레임만 가능

```

### print vs cat

print : 하나의 값을 출력할 때, 데이터프레임과 같은 2차원 자료구조를 출력할 때, 출력 후 자동 줄바꿈

cat : 여러 개의 값을 연결해서 출력할 때, 출력 후 줄바꿈을 하려면 '\n' 
