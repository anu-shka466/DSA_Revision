# Segregate 0s and 1s

**Pattern:** Two Pointers  
**Approach:** In-place swapping

## Approach
1. Initialize `left = 0` and `right = arr.length - 1`.
2. If `arr[left] == 1`, swap `arr[left]` and `arr[right]`.
3. If `arr[left] == 0`, increment `left`.
4. If `arr[right] == 1`, decrement `right`.
5. Repeat until `left >= right`.

## Java Code

```java
class Solution {
    void segregate0and1(int[] arr) {
        int left = 0;
        int right = arr.length - 1;

        while (left < right) {
            if (arr[left] == 1) {
                int temp = arr[left];
                arr[left] = arr[right];
                arr[right] = temp;
            }

            if (arr[left] == 0) left++;
            if (arr[right] == 1) right--;
        }
    }
}
