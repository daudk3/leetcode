Given an array of integers `nums` and an integer `target`, return _indices of the two numbers such that they add up to `target`_.

You may assume that each input would have **_exactly_ one solution**, and you may not use the _same_ element twice.

You can return the answer in any order.

**Example 1:**

**Input:** nums = [2,7,11,15], target = 9
**Output:** [0,1]
**Explanation:** Because nums[0] + nums[1] == 9, we return [0, 1].

**Example 2:**

**Input:** nums = [3,2,4], target = 6
**Output:** [1,2]

**Example 3:**

**Input:** nums = [3,3], target = 6
**Output:** [0,1]

**Constraints:**

- `2 <= nums.length <= 104`
- `-109 <= nums[i] <= 109`
- `-109 <= target <= 109`
- **Only one valid answer exists.**

Solution (Java):
```java
class Solution {
	public int[] twoSum(int[] nums, int target) {

		// Define variables
		int[] ans = new int[2];
		int i = 0;
		int j = 0;
		boolean found = false;
	
		i = 0;
		while (i < nums.length && found == false) {
		// Prevent recounts by starting inner iterator at i+1
			j = i + 1;
			while (j < nums.length && found == false) {
				if (nums[i] + nums[j] == target) {
					found = true;
				}
				// Iterator values not modified once indices found
				if (found == false) {
					j++;
				}
			}
			if (found == false) {
			i++;
			}
		}

		ans[0] = i;
		ans[1] = j;

		return ans;
	}
}
```