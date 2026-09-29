# Two Sum

Find two numbers in `nums` that add up to `target` and return their indices.

## O(n²) Solution

```python
class Solution:
    def twoSum(self, nums: list[int], target: int) -> list[int]:
        for i in range(len(nums)):
            for j in range(i + 1, len(nums)):
                if target == nums[i] + nums[j]:
                    return [i, j]
````

**Time:** `O(n²)`
**Space:** `O(1)`

Two nested `for` loops = `O(n²)`.

## O(n) Dictionary Solution

```python
class Solution:
    def twoSum(self, nums: list[int], target: int) -> list[int]:
        seen = {}

        for i in range(len(nums)):
            needed = target - nums[i]

            if needed in seen:
                return [seen[needed], i]

            seen[nums[i]] = i
```

**Time:** `O(n)`
**Space:** `O(n)`

### Notes

* `nums[i]` = value at index `i`
* `seen = {}` = empty dictionary
* `seen[nums[i]] = i` = store `number -> index`
* `needed = target - nums[i]` = number needed to reach target
* `needed in seen` = check if we already saw it
* `==` = comparison
* `=` = assignment


