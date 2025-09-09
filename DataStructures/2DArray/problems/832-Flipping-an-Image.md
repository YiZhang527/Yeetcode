# LeetCode 832 - Flipping an Image

## Approach: Reverse + XOR
- Flip each row horizontally using reverse()
- Invert each element using XOR (x ^ 1)

## Code1
```Python
class Solution:
    def flipAndInvertImage(self, image: List[List[int]]) -> List[List[int]]:
        for i in range(len(image)):
            image[i].reverse()
            image[i] = [j ^ 1 for j in image[i]]
        return image
```

## Code2
```Python
class Solution:
    def flipAndInvertImage(self, image: List[List[int]]) -> List[List[int]]:
        for row in image:
            n = len(row)
            for i in range((n + 1) // 2):
                row[i], row[n-1-i] = row[n-1-i] ^ 1, row[i] ^ 1
        return image
```
