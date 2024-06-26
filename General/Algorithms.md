#java #alogrithms 
### Euclidean - For finding Greatest common division

```java
while(num2 != 0) {
	int temp = num2;
	num2 = num1 % num2;
}
return num2;
```

### Kadane's - Finding the maximum sum of contiguous subarray within one dimensional array

```java
class Solution {

    public int maxSubArray(int[] nums) {

        int currentSum = nums[0];

        int maxSum = nums[0];

  

        for (int i = 1; i < nums.length; i++) {

            currentSum = Math.max(nums[i], currentSum + nums[i]);

            maxSum = Math.max(currentSum, maxSum);

        }

  

        return maxSum;

    }

}
```

### Sieve of Eratosthenes - Finding the prime number upto given limit

```java
//Sieve of Eratosthenes

  

class Solution {

    public int countPrimes(int n) {

        if(n <= 2) return 0;

  

        boolean isPrime[] = new boolean[n];

        for(int i = 3; i < n; i += 2) {

            isPrime[i] = true;

        }

        isPrime[2] = true;

  

        for(int i = 3; i * i < n; i += 2) {

            if(isPrime[i]) {

                for(int j = i * i; j < n; j += 2 * i) {

                    isPrime[j] = false;

                }

            }

        }

  

        int count = 0;

        for(int i = 2; i < n; i++) {

            if(isPrime[i]) count++;

        }

        return count;

    }

}
```