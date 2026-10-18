# Two Sum — LeetCode 1

**Pattern:** HashMap + Complement Search

## Approach
1. Calculate `req = target - nums[i]`.
2. If `req` exists in the map, return both indices.
3. Otherwise, store `nums[i] → i`.
4. **Check first, insert second** to avoid reusing the same element.

## Java Code
```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer, Integer> map = new HashMap<>();

        for (int i = 0; i < nums.length; i++) {
            int req = target - nums[i];

            if (map.containsKey(req)) {
                return new int[]{map.get(req), i};
            }

            map.put(nums[i], i);
        }

        return new int[]{-1, -1};
    }
}
