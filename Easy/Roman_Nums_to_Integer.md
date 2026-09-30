# Roman to Integer

## Approach

Map each Roman numeral to an index and use that index to access its value.

For each pair of characters:

* Detect the six subtraction cases using their indices.
* Subtract when a smaller numeral comes before a larger one.
* Otherwise, add the current value.
* Process the final character separately if needed.

## Solution

```python
class Solution:
    def romanToInt(self, s: str) -> int:

        char = list(s)

        roman = ["I", "V", "X", "L", "C", "D", "M"]
        value = [1, 5, 10, 50, 100, 500, 1000]

        total = 0
        i = 0

        while i < len(char) - 1:

            current = roman.index(char[i])
            next = roman.index(char[i + 1])

            if (next == 1 or next == 2) and current == 0:
                total += value[next] - value[current]
                i += 2

            elif (next == 3 or next == 4) and current == 2:
                total += value[next] - value[current]
                i += 2

            elif (next == 5 or next == 6) and current == 4:
                total += value[next] - value[current]
                i += 2

            else:
                total += value[current]
                i += 1

        if i < len(char):
            total += value[roman.index(char[i])]

        return total
```

## Complexity

* **Time:** O(n)
* **Space:** O(n)
