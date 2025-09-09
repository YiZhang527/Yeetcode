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
        m, n = len(image), len(image[0])
        for i in range(m):
            for j in range((n + 1) // 2):
                image[i][j], image[i][n-1-j] = image[i][n-1-j] ^ 1, image[i][j] ^ 1
        return image
```
