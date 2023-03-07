# insertion_sort
## 설명
### 자료구조
: 효율적인 접근 및 수정을 가능케 하는 자료의 조직, 관리, 저장을 의미한다.<br>
### 정렬
: 데이터를 특정한 기준에 따라서 순서대로 나열하는 것이다.<br>
정의 만으로 알고리즘을 유추할 수 있도록 한다.<br>
정렬할 원소보다 아래 인덱스에 있는 요소와 비교하기 위함이다.<br>
### 삽입 정렬의 시간 복잡도
->예를들어 [5, 4, 3, 2, 1]과 같은 최악의 경우에는 각각의 탐색에서 무조건 앞의 모든 원소를 뒤로 미뤄버리는 작업을 해야하기 때문에, 시간 복잡도는 O(n^2)이다.
# JAVA 삽입 정렬
```java
public static void main(String[] args) {
	nums = new int[10];
		for (int i = 0; i < 10; i++) {
			nums[i] = (int) (Math.random() * 10);
		}
		System.out.println("<정렬 전>");
		System.out.println(Arrays.toString(nums));
		
		for(int i = 1; i < nums.length; i++) {
			// 현재 선택된 원소의 값을 임시 변수에 저장해준다.
			int temp = nums[i];
			// 현재 원소를 기준으로 이전 원소를 탐색하기 위한 index 변수.
			int prev = i - 1;
			// 현재 선택된 원소가 이전 원소보다 작은 경우까지만 반복. 단, 0번째 원소까지만 비교한다.
			while(prev >= 0 && nums[prev] > temp) {
				// 현재 선택된 원소가 현재 탐색중인 원소보다 작다면, 해당 원소는 다음 인덱스로 미뤄버린다.
				nums[prev + 1] = nums[prev];
				// 다음 대상 원소를 탐색한다.
				prev--;
			}
			// 탐색이 종료된 지점에 현재 선택되었던 변수의 값을 삽입해준다.
			nums[prev + 1] = temp;
		}
		
		System.out.println("<정렬 후>");
		System.out.println(Arrays.toString(nums));
	}
}
```

# bubble_sort

## 방법
1. 앞에서부터 현재 원소와 바로 다음의 원소를 비교한다.

2. 현재 원소가 다음 원소보다 크면 원소를 교환한다.

3. 다음 원소로 이동하여 해당 원소와 그 다음원소를 비교한다.<br>

## 장점과 단점
#### 1) 장점

    1.안정한 정렬 방법(바로 옆의 데이터와 비교하기 때문)
    2.자료의 수가 적을 경우 알고리즘 구현이 매우 간단
    3.이미 정렬되어 있는 경우나 자료의 수가 적은 정렬에 매우 효율적
#### 2) 단점

    1.비교적 많은 레코드들의 이동을 포함
    2.자료의 수가 많고 자료의 크기가 클 경우 적합하지 않음

## 예시
![img (1)](https://user-images.githubusercontent.com/123055714/223298766-21c0784f-4a93-4b57-836f-aec76a856308.png)
