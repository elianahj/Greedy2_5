## 1. 문제 (작성자 : 정현화)
n개의 정수로 이루어진 수열이 있다. 
이 수열에서 한 정수를 제거하거나, 또는 두 정수를 제거할 수 있다. 
한 정수를 제거하는 경우에는 그 정수가 점수가 되고, 
두 정수를 제거하는 경우에는 두 정수의 곱이 점수가 된다. 
이를 반복하여 수열에 아무 수도 남지 않게 되었을 때, 
점수의 총 합의 최대를 구하는 프로그램을 작성하시오.

예를 들어 -1, 5, -3, 5, 1과 같은 수열이 있다고 하자. 먼저 1을 제거하고, 
다음으로는 5와 5를 제거하고, 다음에는 -1과 -3을 제거했다고 하자. 
이 경우 각각 점수가 1, 25, 3이 되어 총 합이 29가 된다.

## 2. 알고리즘
그리디 알고리즘 : 최적의 방법 선택

합의 최대를 구하려면 음수끼리 두개씩 빼야한다
	*수열의 갯수가 홀수인 경우
 	i) 음수가 짝수개인 경우
	한개의 정수를 뺄때
		- 가장 작은 양수 빼기
	두개의 정수를 뺄 때
		- 음수 두개 선택 양수를 만듦
		- 큰 정수 두개 선택
	 ii) 음수가 홀수개인 경우 
	한개의 정수를 뺄때
		- 절댓값이 가장 작은 음수 빼기
	두개의 정수를 뺄때
		-큰 정수 두개 선택
	* 수열의 갯수가 짝수인 경우
	한개의 정수를 뺄때
		- 절댓값이 가장 작은 음수 빼기
	두개의 정수를 뺄때
		-큰 정수 두개 선택 

## 3. 코드
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
