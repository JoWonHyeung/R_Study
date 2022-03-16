# R

## 3/15

- #### Boolean값 비교

     Javascript: true, false

     R: TRUE, FALSE, T, F

     Python: True, False

## 3/16

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
          
rev : 역순 출력

range : 최소, 최대 출력

sort(x, decreasing = TRUE) : 정렬, 정렬 순서의 default는 오름차순

order : 정렬된 index 출력

         ex) x <- order(10,20,7,14,15) 
             3 1 4 5 2 출력 -> 가장 작은 값인 7은 벡터 3번째에 존재한다.
             
which : 조건에 맞는 특정 위치들을 찾을 수 있다.

which.max : 벡터내에서 가장 큰 값의 index값을 반환

which.min : 벡터내에서 가장 작은 값의 index값을 반환한다.

sample(벡터, 몇 개를 뽑을지, replace=복원 추출 or 비복원 추출) : 랜덤값 출력, replace의 default 값은 False

paste (..., sep = " ", collapse = NULL) : 나열된 원소 사이에 공백을 두고 결과값을 출력합니다.

paste0(..., collapse = NULL) : 나열된 원소 사이에 공백없이 출력합니다.

summary : 기술통계함수
