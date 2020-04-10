### 성공적인 코딩 인터뷰를 위한 코딩 인터뷰 정복하기 – 코딩 테스트

## Section 3. 정렬

1. 거품정렬(Bubble Sort, 버블 정렬)
   - 거품정렬(속칭 버블정렬)은 첫 번째 요소와 두 번째 요소와의 비교를 시작함으로서 시작하며
     오름차순 정렬일 경우 가장 큰 값의 요소를 한 번 루핑시 가장 오른쪽에 배치하게 됩니다.
     그렇게 자료 n개가 있을 경우 처음엔 n-1번 비교... 1번 비교하게 되면서
     시간복잡도 O(n^2)를 가지고 비교하고 바꾸는데 하나의 공간이 필요하게 되면서
     공간복잡도 O(1)을 가지고 있으나 요즘엔 공간이 
2. 선택정렬(Selection Sort)
   - 선택정렬은 루핑하면서 가장 작은 값을 찾아내 이미 확정이 되지 않은 요소 중 가장 앞의 요소와 바꾸는
     정렬 알고리즘입니다.
   - 앞에서 말했던 것처럼 루핑하면서 가장 작은 값을 찾아낸 뒤 앞에서부터 확정을 시키면서 정렬을 하게
     되는데 루핑은 n-1번 하게 되며 따라서 시간복잡도 O(n^2)으로 매우 느리지만 쉽게 구현할 수 있어서
     은근히 쓰입니다. 공간복잡도는 O(1)으로써 가장 작은 값을 담아두고 있을 공간이 필요하기 때문입니다.
3. 삽입정렬(Insertion Sort)
   - 삽입정렬은 말 그대로 새로운 정렬된 리스트에 기존의 요소를 넣으면서 비교하며 정렬하는 정렬 알고리즘입니다.
   - 앞에서 말했던 것처럼 요소를 처음부터 시작해서 모두 새로운 리스트에 집어넣는데
     이때 정렬된 리스트의 가장 오른쪽에 둡니다. 오름차순일 경우 가장 작은 값이 왼쪽에 가도록
     오른쪽에서 왼쪽 방향으로 비교하면서 정렬을 시킵니다.
   - 시간복잡도는 O(n^2)으로 좋지 않지만 쉽게 구현할 수 있어서 많이 쓰인다.
4. 병합정렬(Merge Sort)
   - 병합정렬은 리스트를 나누었다가 비교하며 다시 병합시키면서 정렬하는 정렬 알고리즘이다.
   - 병합정렬은 리스트를 나누면서 요소가 1개 또는 0개가 될 때 까지 나누게 되는데
     이 때 시간복잡도 O(logn)이 발생하게 되고 다시 비교하며 합치게 될 때
     비교하는 횟수가 n개 이므로 O(n)이 발생하게 되어 총 O(nlogn)이 발생하게 됩니다.
5. 퀵 정렬(Quick Sort)
   - 퀵 정렬은 리스트에 임의의 요소인 피벗(Pivot)을 설정하여 그 피벗을 기준으로 나눠서 분할, 정복, 결합을
     통해 정렬을 하는 정렬 알고리즘이다.
   - 임의의 요소 피벗을 제외하고 가장 왼쪽의 값을 low, 가장 오른쪽의 값을 high라고 할 때,
     low의 값이 피벗보다 작을 땐 low의 포인터를 한 칸 오른쪽으로 옮깁니다.
     high의 값이 피벗보다 클 땐 high의 포인터를 한 칸 왼쪽으로 옮깁니다.
     low의 값이 피벗보다 크고 high의 값이 피벗보다 작을 때 그 둘의 값을 스와핑합니다.
     만약 low보다 high가 왼쪽에 있다면 high의 값과 피벗의 값을 스와핑 합니다.
     이렇게 변경하면 피벗을 기준으로 왼쪽에는 피벗보다 작은 값이, 오른쪽에는 피벗보다 큰 값이 오게 됩니다.
     다시 피벗을 제외하고 왼쪽과 오른쪽이 새로운 리스트가 되어 피벗을 정하고 위를 반복하면서 정렬합니다.
     이 퀵 정렬은 시간복잡도 O(nlogn)을 가지지만 최악의 경우에는 O(n^2)의 시간복잡도를 가집니다.
     하지만 정상적인 경우에 대부분 가장 빠른 정렬이라고 해서 퀵 정렬이라고 합니다.
