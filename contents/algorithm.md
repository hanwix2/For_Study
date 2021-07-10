# Algorithm

## :memo: Contents
- [정렬](#정렬sort)
    - [선택 정렬](#label-선택-정렬selection-sort)

---

# 정렬(Sort)

## :label: 선택 정렬(selection sort)

- 원리:
    - 배열에서 가장 큰 원소를 찾아 이 원소와 배열의 끝자리와 바꾼다.
    - 이 원소를 제외한 나머지 원소들도 같은 작업으로 뒤에서부터 차례로 바꾼다.
    > **"가장 큰 것 찾아서 뒤로 보내기"**

- pseudo code
```java
selectionSort(A[], n) {             // A[1...n]을 정렬
    for last <- n downto 2 {
        k <- the largest A[k] in A[1...last];
        A[k] ⇔ A[last];
    }
}
```

- 수행 시간: **Θ(n²)**

<br>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#algorithm)

<br>
<br>

## :label: 버블 정렬(bubble sort)

- 원리:
    - 왼쪽부터 차례로 이웃한 수를 비교하면서 큰 수를 오른쪽으로 보낸다.
    - 위의 작업 루프를 모든 배열이 정렬될 때까지 계속 돌린다.
    > **"인접한 것을 순서대로 맞춰 나간다."**

- pseudo code
    ```java
    bubbleSort(A[], n) {
        for last <- n downto 2 {
            for i <- 1 to (last-1)
                if (A[i] > A[i+1]) then A[i] ⇔ A[i+1];
        }
    }
    ```

- 수행 시간: **Θ(n²)**

<br>

> :house: [home](https://github.com/hanwix2/For_Study) :top: [top](#algorithm)
