# Greedy2_5

## 1. 그리디(Greedy) 알고리즘이란? (작성자 : 한현진)
- 최적화 문제를 해결하는 알고리즘
  * 최적화 문제 : 가능한 해들 중에서 가장 좋은 (최대 또는 최소) 해를 찾는 문제
- 입력 데이터 간의 관계를 고려하지 않고 수행 과정에서 ```욕심내어``` 최소값 또는 최대값을 가진 데이터를 선택
  * 이러한 선택을 ```근시안적```인 선택이라고 말하기도 함
- 근시안적인 선택으로 부분적인 최적해를 찾고, 이들을 모아서 문제의 최적해를 얻는다.
- 일단 한 번 선택하면, 이를 절대로 번복하지 않는다.
- 이러한 특성 때문어 대부분의 그리디 알고리즘 들은 매우 단순하며, 또한 제한적인 문제들만이 그리디 알고리즘으로 해결된다.
- 그리디 알고리즘의 수행 과정
- 
![image](https://user-images.githubusercontent.com/80517119/114831545-7a142680-9e08-11eb-8cea-aba1af9b7a0d.png)

## 2. 그리디 알고리즘의 예 - 부분 배낭 문제 (작성자 : 한현진)
- 부분 배낭 문제에서는 물건을 부분적으로 배낭에 담을 수 있으므로, 최적해를 위해서 ```욕심을 내어``` 단위 무게 당 가장 값나가는 물건을 배낭에 넣고, 계속해서 그 다음으로 값나가는 물건을 넣는다.

- 부분 배낭 문제의 그리디 알고리즘
  * 입력 : n개의 물건, 각 물건의 무게(w)와 가치(v), 배낭의 용량 C
  * 출력 : 배낭에 담은 물건들의 가치의 합의 최대값
  * 1. 각 물건의 단위 무게 당 가치를 계산하여 물건들을 내림차순으로 정렬
  * 2. while문
  단위 무게당 가치가 가장 높은 물건들을 차례로 배낭에 담는다. 배낭의 용랑이 초과되면 종료
  * 3. if문
  현재까지 배낭에 담은 물건들의 무게 w가 배낭의 용량 C보다 작으면, 해당 물건을 배낭에 담고 가치를 증가시킴
  * 4. 배낭에 담긴 물건들의 가치의 합을 리턴

## 3. Java 구현 (작성자 : 한현진)



## 4. 시간 복잡도 (작성자 : 한현진)
- n개의 물건 각각의 단위 무게 당 가치를 계산 => ```O(n)```
- 물건의 단위 무게 당 가치에 대해서 내림차 순으로 정렬 => ```O(nlogn)```
- while문 수행 횟수 =< n, 1번 수행 당 걸리는 시간 = O(1) => ```n x O(1)```
- 각각의 if문 수행 시 걸리는 시간 => ```O(n)```
- 알고리즘의 시간복잡도
  * O(n)+O(nlogn)+n x O(1)+O(n) = **O(nlogn)**
