class Solution:
    def findMaxAverage(self, nums: List[int], k: int) -> float:
        n = len(nums)
        windowSum = sum(nums[:k])
        maxSum = windowSum
        for i in range(k, n):
            windowSum += nums[i]
            windowSum -= nums[i-k]
            if windowSum > maxSum:
                maxSum = windowSum
        return maxSum/k
