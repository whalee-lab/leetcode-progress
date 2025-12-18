## Title: 3Sum Closest

## Link:
[https://leetcode.com/problems/two-sum/](https://leetcode.com/problems/3sum-closest/description/?envType=problem-list-v2&envId=sorting)

## Difficulty:
Medium

## Tags:
Array, Two Pointer, Sorting

## Approach
Short explanation (3–5 lines).

### Code
```python
class Solution:
    def threeSumClosest(self, nums: List[int], target: int) -> int:
        nums.sort()
        closest_sum = float('inf')
        min_diff = float('inf')

        for i in range(len(nums) - 2):
            left, right = i + 1, len(nums) - 1

            while left < right:
                current_sum = nums[i] + nums[left] + nums[right]
                current_diff = abs(current_sum - target)

                if current_diff < min_diff:
                    min_diff = current_diff
                    closest_sum = current_sum

                if current_sum < target:
                    left += 1
                else:
                    right -= 1
        return closest_sum
```
### Complexity
Time: O(n^2)
Space: O(n)
