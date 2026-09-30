# Palindrome Number

Determine whether an integer reads the same forward and backward.

## Solution

```python
class Solution:
    def isPalindrome(self, x: int) -> bool:
        if x < 0:
            return False

        s = str(x)
        i = 0
        j = len(s) - 1

        while i < len(s) // 2:
            if s[i] != s[j]:
                return False

            i += 1
            j -= 1

        return True
