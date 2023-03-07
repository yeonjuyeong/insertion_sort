# insertion_sort
### 방법
1. 현재 타겟이 되는 숫자와 이전 위치에 있는 원소들을 비교한다. (첫 번째 타겟은 두 번째 원소부터 시작한다.)

2. 타겟이 되는 숫자가 이전 위치에 있던 원소보다 작다면 위치를 서로 교환한다.

3. 그 다음 타겟을 찾아 위와 같은 방법으로 반복한다. <br>

### 장점과 단점
##### 1) 장점

1. 추가적인 메모리 소비가 작다.
2. 거의 정렬 된 경우 매우 효율적이다. 즉, 최선의 경우 O(N)의 시간복잡도를 갖는다.
3. 안장정렬이 가능하다.
##### 1) 단점

1. 역순에 가까울 수록 매우 비효율적이다. 즉, 최악의 경우 O(N2)의 시간 복잡도를 갖는다.
2. 데이터의 상태에 따라서 성능 편차가 매우 크다. 

### 예시
  start<br>
 2 4 1 3 5<br>
  pass 1<br>
 2 1 4 3 5
 
  pass 2<br>
 1 2 4 3 5
 
  pass 3<br>
 1 2 3 4 5
## JAVA 삽입 정렬
```java
package sort;
import java.util.*;
public class insertion_sort {
	static int[] nums;

	public static void main(String[] args) {
		// TODO Auto-generated method stub
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
## 결과
![image](https://user-images.githubusercontent.com/123055714/223324447-7406228f-b9f4-4948-aa4e-076a8ba3d376.png)

# bubble_sort

### 방법
1. 앞에서부터 현재 원소와 바로 다음의 원소를 비교한다.

2. 현재 원소가 다음 원소보다 크면 원소를 교환한다.

3. 다음 원소로 이동하여 해당 원소와 그 다음원소를 비교한다.<br>

### 장점과 단점
##### 1) 장점

    1.안정한 정렬 방법(바로 옆의 데이터와 비교하기 때문)
    2.자료의 수가 적을 경우 알고리즘 구현이 매우 간단
    3.이미 정렬되어 있는 경우나 자료의 수가 적은 정렬에 매우 효율적
##### 2) 단점

    1.비교적 많은 레코드들의 이동을 포함
    2.자료의 수가 많고 자료의 크기가 클 경우 적합하지 않음

### 예시

  start<br>
 4 2 1 6 5 3 <br>
 pass 1<br>
 2 1 4 5 3 6
 
 pass 2<br>
 1 2 4 3 5 6
 
 pass 3<br>
 1 2 3 4 5 6
 
 ## JAVA 버블 정렬
 ```java
 public class BubbleSort {
 
    public static void bubbleSort(int[] array) {
        for (int i = 0; i < array.length; i++) {
            for (int j = 0; j < array.length - i - 1; j++) {
                if (array[j] > array[j + 1]) {
                    swap(array, j, j + 1);
                }
            }
        }
    }
 
    public static void swap(int[] array, int source, int target) {
        int temp = array[source];
        array[source] = array[target];
        array[target] = temp;
 
    }
 
    public static void printArray(int[] array) {
        for (int data : array) {
            System.out.print(data + " ");
        }
        System.out.println();
    }
 
    public static void main(String[] args) {
        int[] item = new int[] { 5, 3, 8, 1, 2, 7 };
        System.out.println("정렬 전");
        printArray(item);
        bubbleSort(item);
        System.out.println("정렬 후");
        printArray(item);
 
    }
 
}
''''
