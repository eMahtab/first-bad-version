# First bad version
## https://leetcode.com/problems/first-bad-version

# Implementation 1 : Naive(Brute Force) Time Limit Exceeded O(n)
```java
/* The isBadVersion API is defined in the parent class VersionControl.
      boolean isBadVersion(int version); */

public class Solution extends VersionControl {
    public int firstBadVersion(int n) {
        for(int i = 1; i <= n; i++) {
            if(isBadVersion(i))
                return i;
        }
        return -1;
    }
}
```

# Implementation 2 : Binary Search  O(logn)
```java
/* The isBadVersion API is defined in the parent class VersionControl.
      boolean isBadVersion(int version); */

public class Solution extends VersionControl {
    public int firstBadVersion(int n) {
        int left = 1;
        int right = n;
        while(left < right) {
            int mid = left + (right-left)/2;
            if(!isBadVersion(mid)) {
                left = mid+1;
            } else {
                right = mid;
            }
        }
        return left;
    }
}
```

# References :
https://leetcode.com/problems/first-bad-version/solution
