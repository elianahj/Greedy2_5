# Greedy2_5

## 참여자 : 한현진, 정현화
## 불참자 : 원장연

## 1. 그리디(Greedy) 알고리즘이란? (작성자 : 한현진)
- 최적화 문제를 해결하는 알고리즘
  * 최적화 문제 : 가능한 해들 중에서 가장 좋은 (최대 또는 최소) 해를 찾는 문제
- 입력 데이터 간의 관계를 고려하지 않고 수행 과정에서 ```욕심내어``` 최소값 또는 최대값을 가진 데이터를 선택
  * 이러한 선택을 ```근시안적```인 선택이라고 말하기도 함
- 근시안적인 선택으로 부분적인 최적해를 찾고, 이들을 모아서 문제의 최적해를 얻는다.
- 일단 한 번 선택하면, 이를 절대로 번복하지 않는다.
- 이러한 특성 때문어 대부분의 그리디 알고리즘 들은 매우 단순하며, 또한 제한적인 문제들만이 그리디 알고리즘으로 해결된다.
- 그리디 알고리즘의 수행 과정

![image](https://user-images.githubusercontent.com/80517119/114831545-7a142680-9e08-11eb-8cea-aba1af9b7a0d.png)

## 2. 문제 (작성자 : 정현화)
n개의 정수로 이루어진 수열이 있다. 
이 수열에서 한 정수를 제거하거나, 또는 두 정수를 제거할 수 있다. 
한 정수를 제거하는 경우에는 그 정수가 점수가 되고, 
두 정수를 제거하는 경우에는 두 정수의 곱이 점수가 된다. 
이를 반복하여 수열에 아무 수도 남지 않게 되었을 때, 
점수의 총 합의 최대를 구하는 프로그램을 작성하시오.

예를 들어 -1, 5, -3, 5, 1과 같은 수열이 있다고 하자. 먼저 1을 제거하고, 
다음으로는 5와 5를 제거하고, 다음에는 -1과 -3을 제거했다고 하자. 
이 경우 각각 점수가 1, 25, 3이 되어 총 합이 29가 된다.

## 2-1. 알고리즘 (작성자 : 정현화)
그리디 알고리즘 : 최고의 방법 선택

합의 최대를 구하려면 음수끼리 두개씩 빼야한다
* 수열의 갯수가 홀수인 경우
*i) 음수가 짝수개인 경우
*한개의 정수를 뺄때
- 가장 작은 양수 빼기
*두개의 정수를 뺄 때
- 음수 두개 선택 양수를 만듦
- 큰 정수 두개 선택
	*ii) 음수가 홀수개인 경우 
		*한개의 정수를 뺄때
		- 절댓값이 가장 작은 음수 빼기
		*두개의 정수를 뺄때
		-큰 정수 두개 선택
		
* 수열의 갯수가 짝수인 경우
	*한개의 정수를 뺄때
		- 절댓값이 가장 작은 음수 빼기
	*두개의 정수를 뺄때
		-큰 정수 두개 선택 

## 2-2. 코드 (작성자 : 정현화)
```
package com.company;

public class Class{
    public static int test(String[] ar){ // 음수값 갯수세기
        int neg = 0;
        for(int i=0;i< 100;i++){
            if(i< 0){
                neg++;}
        }
        return neg;
    }
    public static int plus(String[] ar) { //배열에 저장해둔 값 더하기
        int key = 0;

        for (int i = 0; i < ar.length; i++) {
            key = key + i;
        }
        return key;
    }
    public static int negpro(int[] ar){ // 가장 큰 양수 찾고 곱
        int neg = -1;
        int neg1 = 0;
        for (int i = 0; i < ar.length; i++) {
            if (i <= neg){
                i = neg1;
                i = neg;
            }
        }
        return neg1*neg;
    }

    public static int min(int[] ar){ // 가장 작은 양수 찾기

        int min = 1;
        for (int i = 0; i < ar.length; i++) {
            if (i< min){
                min = i;
            }
        }
        return min;
    }
    public static int maxpro(int[] ar){ // 가장 큰 양수 찾고 곱
        int max = 0;
        int max2 =0;
        int[] arr = {};
        for (int i = 0; i < arr.length; i++) {
            if (i > max){
                max = i;
                max = max2;
            }
        }
        return max*max2;
    }

    }
    public static void main(String[] args) {
        int[] arr = {};// 배열생성
        int[] out_arr = {}; //출력배열 생성
        int neg = 0;

        if (arr.length % 2 != 0) {

                if (neg % 2 != 0){
                    return min(arr) + maxpro(arr) + negpro(arr)
                }
                }

        if (arr.length % 2 == 0) {
            if (neg % 2 == 0){
                return min(arr) + maxpro(arr) + negpro(arr)
            }
    }
```


## 3. 그리디 알고리즘의 예 - 부분 배낭 문제 (작성자 : 한현진)
- 부분 배낭 문제에서는 물건을 부분적으로 배낭에 담을 수 있으므로, 최적해를 위해서 ```욕심 내어``` 단위 무게 당 가장 값나가는 물건을 배낭에 넣고, 계속해서 그 다음으로 값나가는 물건을 넣는다. 배낭의 용량을 초과해서 담을 수는 없다.
- 부분 배낭 문제의 그리디 알고리즘 구현 과정
  * 입력 : n개의 물건, 각 물건의 무게(w)와 가치(v), 배낭의 용량 C
  * 출력 : 배낭에 담은 물건들의 가치의 합의 최대값 
  * 1) 각 물건의 단위 무게 당 가치를 계산하여 물건들을 내림차순으로 정렬
  * 2) while문
  단위 무게당 가치가 가장 높은 물건들을 차례로 배낭에 담는다. 배낭의 용랑이 초과되면 종료
  * 3) if문
  현재까지 배낭에 담은 물건들의 무게 w가 배낭의 용량 C보다 작으면, 해당 물건을 배낭에 담고 가치를 증가시킴
  * 4. 배낭에 담긴 물건들의 가치의 합을 리턴

## 3-1. Java 구현 (작성자 : 한현진)
- 입출력
![image](https://user-images.githubusercontent.com/80517119/114845830-10e7df80-9e17-11eb-8654-aea1d05431d3.png)

- 부분적으로 배낭에 담는 과정 
![image](https://user-images.githubusercontent.com/80517119/114846212-6cb26880-9e17-11eb-8485-751fac979c5a.png)

- 실행 결과 

![image](https://user-images.githubusercontent.com/80517119/114846518-bf8c2000-9e17-11eb-997f-3bde8492a4b2.png)

## 3-2. 시간 복잡도 (작성자 : 한현진)
- n개의 물건 각각의 단위 무게 당 가치를 계산 => ```O(n)```
- 물건의 단위 무게 당 가치에 대해서 내림차 순으로 정렬 => ```O(nlogn)```
- while문 수행 횟수 =< n, 1번 수행 당 걸리는 시간 = O(1) => ```n x O(1)```
- 각각의 if문 수행 시 걸리는 시간 => ```O(n)```
- 알고리즘의 시간복잡도
  * O(n)+O(nlogn)+n x O(1)+O(n) = **```O(nlogn)```**
